<template>
  <div class="scroll-wrapper">
    <!-- scrollable area (slot holds your content) -->
    <div ref="content" class="scroll-content" @scroll="onScroll">
      <slot />
    </div>

    <!-- custom scrollbar (hidden automatically if no overflow) -->
    <div class="custom-scrollbar" ref="scrollbar" aria-hidden="true">
      <div
        ref="thumb"
        class="custom-thumb"
        :style="{ height: thumbHeight + 'px', top: thumbTop + 'px' }"
        @pointerdown.prevent="onPointerDown"
      />
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted, onBeforeUnmount, nextTick } from 'vue'

const content = ref<HTMLElement | null>(null)
const thumb = ref<HTMLElement | null>(null)
const scrollbar = ref<HTMLElement | null>(null)

const thumbHeight = ref(0)
const thumbTop = ref(0)

let dragging = false
let startPointerY = 0
let startScrollTop = 0

let ro: ResizeObserver | null = null
let mo: MutationObserver | null = null

const clamp = (v: number, a = 0, b = Number.POSITIVE_INFINITY) =>
  Math.max(a, Math.min(b, v))

function updateThumb() {
  if (!content.value || !scrollbar.value || !thumb.value) return

  const contentEl = content.value
  const trackH = scrollbar.value.clientHeight
  const visible = contentEl.clientHeight
  const total = contentEl.scrollHeight

  // No overflow -> hide thumb
  if (total <= visible) {
    thumb.value.style.display = 'none'
    thumbHeight.value = 0
    thumbTop.value = 0
    return
  } else {
    thumb.value.style.display = ''
  }

  // Thumb height proportional to visible/total
  const minThumb = 20
  const h = Math.max((visible / total) * trackH, minThumb)
  thumbHeight.value = h

  // Thumb position must map scrollTop -> [0, trackH - h]
  const maxScroll = total - visible
  const maxThumbTop = trackH - h
  const top = (contentEl.scrollTop / maxScroll) * maxThumbTop
  thumbTop.value = clamp(top, 0, maxThumbTop)
}

function onScroll() {
  updateThumb()
}

function onPointerDown(e: PointerEvent) {
  if (!content.value || !thumb.value) return
  dragging = true
  startPointerY = e.clientY
  startScrollTop = content.value.scrollTop
  document.body.style.userSelect = 'none'

  // capture pointer so pointermove events go to us
  try { (thumb.value as HTMLElement).setPointerCapture?.(e.pointerId) } catch {}

  window.addEventListener('pointermove', onPointerMove)
  window.addEventListener('pointerup', onPointerUp)
}

function onPointerMove(e: PointerEvent) {
  if (!dragging || !content.value || !scrollbar.value) return
  const deltaY = e.clientY - startPointerY
  const total = content.value.scrollHeight
  const visible = content.value.clientHeight
  const trackH = scrollbar.value.clientHeight
  const maxThumbTop = trackH - thumbHeight.value
  if (maxThumbTop <= 0) return
  const scrollPerPx = (total - visible) / maxThumbTop
  content.value.scrollTop = startScrollTop + deltaY * scrollPerPx
}

function onPointerUp(e: PointerEvent) {
  dragging = false
  document.body.style.userSelect = ''
  try { thumb.value?.releasePointerCapture?.(e.pointerId) } catch {}
  window.removeEventListener('pointermove', onPointerMove)
  window.removeEventListener('pointerup', onPointerUp)
}

onMounted(() => {
  nextTick(() => {
    updateThumb()
    // scroll listener already attached via @scroll but keep this to be safe
    content.value?.addEventListener('scroll', onScroll)

    // update when content size changes
    ro = new ResizeObserver(updateThumb)
    if (content.value) ro.observe(content.value)

    // update when DOM inside content changes (slot content)
    mo = new MutationObserver(updateThumb)
    if (content.value) mo.observe(content.value, { childList: true, subtree: true, characterData: true })

    window.addEventListener('resize', updateThumb)
  })
})

onBeforeUnmount(() => {
  content.value?.removeEventListener('scroll', onScroll)
  ro?.disconnect()
  mo?.disconnect()
  window.removeEventListener('resize', updateThumb)
})
</script>

<!-- NOTE: remove "scoped" if you find ::-webkit-scrollbar rules not applying -->
<style>
.scroll-wrapper {
  position: relative;
  width: 100%;
  height: 100%;
  overflow: hidden; /* hide native outer scrollbar */
}

/* this is the element that actually scrolls */
.scroll-content {
  height: 100%;
  overflow-y: auto;
  padding-right: 12px; /* leave space so content isn't hidden under custom scrollbar */
  box-sizing: content-box;

  /* hide native scrollbars across browsers */
  -ms-overflow-style: none; /* IE/Edge */
  scrollbar-width: none; /* Firefox */
}
.scroll-content::-webkit-scrollbar {
  display: none; /* Chrome/Safari */
}

/* track */
.custom-scrollbar {
  position: absolute;
  top: 0;
  right: 4px;
  width: 8px;
  height: 100%;
  background: transparent; /* change if you want visible track bg */
  display: flex;
  align-items: flex-start;
}

/* thumb */
.custom-thumb {
  position: absolute;
  right: 0;
  width: 100%;
  border-radius: 6px;
  background: rgb(234, 212, 212);
  cursor: grab;
  transition: background 0.15s;
  touch-action: none; /* allow pointer events to handle touch */
}
.custom-thumb:active { cursor: grabbing; }
.custom-thumb:hover { background: #C0392B; }
</style>

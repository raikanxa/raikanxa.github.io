<script setup lang="ts">
import Navbar from './components/Navbar.vue';
import SideBar from './components/SideBar.vue';
</script>

<template>
<div class="outer-container flex w-full relative min-h-screen">   
<SideBar/>
<div class="relative main-container ml-76 mr-16">
    <div class="flex rounded-[10px] items-center p-[1rem] bg-white text-black shadow-md">
        <div class="flex-col p-[1rem] items-center text-left">
            <div class="text-[36px] font-bold pb-[1rem]">
                I'm <br>
                <span class="text-[red]">
                Fullstack
                </span> 
                Developer
            </div>
            <div class="text-gray-500 text-[14px] pb-[1rem]">
                Proficient at python programming language 
                catered towards backend development in tandem 
                with VueJs for web development. Have designed 
                and developed multiple systems using these and 
                other skills i have accumulated over the years.
            </div>
            <button class="flex gap-2 bg-[red] px-[2rem] py-[0.5rem] rounded-[5px] font-[400] text-[14px]">
                <div>HIRE ME</div> <div><i class="fa-solid fa-arrow-right text-[12px]"></i></div>
            </button> 
        </div>
        <div class="flex">
            <img 
            class="max-w-[200px] max-h-[300px] rounded-lg shadow-lg" 
            src="../src/assets/wallpaperflare.com_wallpaper (19).jpg" 
            alt="profile"
            />
        </div>
    </div>

    <!-- Middle Container -->
    <div class="bg-[#F0F0F6] mt-[2rem] w-[100%]">
        <div class="w-[100%]">
        <h2 class="text-[2rem] text-center font-semibold mb-4">My Services</h2>
        <p class="text-gray-500 text-center">
            These are the services i have come to provide over the years.
        </p>
        </div>
        <div class="flex mt-[1rem] w-full gap-2 justify-around flex-wrap">
            <div class="flex-col bg-white w-[30%] text-center rounded-lg py-[2rem]">
                <div class="p-[0.5rem]"><i class="fa-solid fa-server text-[4rem] text-red-500"></i></div>
                <div class="p-[0.5rem]"><span class="text-[1.2rem] font-[500]">Backend Development</span></div>
                <div class="p-[0.5rem]">                
                <p class="text-gray-500">
                Database design & integration, 
                api design & integration,
                devops, server setup and maintainence
                </p>
                </div>
            </div>
            <div class="flex-col bg-white w-[30%]  text-center rounded-lg py-[2rem]">
                <div class="p-[0.5rem]"><i class="fa-solid fa-laptop-code text-[4rem] text-red-500"></i></div>
                <div class="p-[0.5rem]"><span class="text-[1.2rem] font-[500]">Web Development</span></div>
                <div class="p-[0.5rem]">
                <p class="text-gray-500">
                Website design & implementation, 
                website maintainence, 
                integration with backend
                </p>
                </div>
            </div>
        </div>

    </div>

    <div class="bg-[#F0F0F6] mt-[2rem] w-[100%]">
        <div class="w-[100%]">
        <h2 class="text-[2rem] text-center font-semibold mb-4">Education</h2>
        <p class="text-gray-500 text-center">
        
        </p>
        </div>
        <div class="flex-col bg-white mt-[1rem] p-[1rem] w-full justify-around flex-wrap">
            <div class="flex py-[1.2rem] justify-between border-b-[1.5px] border-gray-300">
                <div class="w-[30%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        Texas College of Management & It
                    </div>
                    <div class="flex gap-[3rem] flex-wrap">
                        <div>Student</div>
                        <div class="text-white text-[12px] bg-red-500 py-[1px] px-[1rem]">
                            2016-2020
                        </div>
                    </div>
                </div>
                <div class="w-[60%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        Bachelor's Certificate
                    </div>
                    <div class="text-gray-500">
                        I have obtained a bachelor's degree in 
                        CSIT(Computer Science Information Technology)
                        from here. While studying here i have learned 
                        various skills pertaining to technology, 
                        academics, communication and profession.
                    </div>
                </div>
            </div>
            <div class="flex py-[1.2rem] justify-between border-b-[1.5px] border-gray-300">
                <div class="w-[30%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        Uniglobe Higher Secondary School
                    </div>
                    <div class="flex gap-[3rem] flex-wrap">
                        <div>Student</div>
                        <div class="text-white text-[12px] bg-red-500 py-[1px] px-[1rem]">
                            2014-2016
                        </div>
                    </div>
                </div>
                <div class="w-[60%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        +2 Degree
                    </div>
                    <div class="text-gray-500">
                        I have obtained a +2 degree in 
                        Science from here and it 
                        opened many doors for me towards 
                        furthering my education and
                        choosing profession.
                    </div>
                </div>
            </div>
        </div>
    </div>

    <div class="bg-[#F0F0F6] mt-[2rem] w-[100%]">
        <div class="w-[100%]">
        <h2 class="text-[2rem] text-center font-semibold mb-4">Work History</h2>
        <p class="text-gray-500 text-center">
            I have worked for a total of 5 years now in the IT field and on this journey 
            have gained alot of experience about work, people and life as a whole during
            this time.
        </p>
        </div>
        <div class="flex-col bg-white mt-[1rem] p-[1rem] w-full justify-around flex-wrap">
            <div class="flex py-[1.2rem] justify-between border-b-[1.5px] border-gray-300">
                <div class="w-[30%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        Professional
                    </div>
                    <div class="flex gap-[3rem] flex-wrap">
                        <div>Student</div>
                        <div class="text-white text-[12px] bg-red-500 py-[1px] px-[1rem]">
                            2022-Current
                        </div>
                    </div>
                </div>
                <div class="w-[60%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        Certificate of Developer Experience
                    </div>
                    <div class="text-gray-500">
                        I joined the company back in mid 2022 as a developer intern and joined as
                        a python developer in a few months along with learning VueJs on the side.
                        I learned some work culture, ethics in a larger company and enhanced my social skills along with
                        professional skills culminating to a position as a Fullstack Developer.
                    </div>
                </div>
            </div>
            <div class="flex py-[1.2rem] justify-between border-b-[1.5px] border-gray-300">
                <div class="w-[30%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        BITSPANDA TECHNOLOGY PVT. LTD.
                    </div>
                    <div class="flex gap-[3rem] flex-wrap">
                        <div>Professional</div>
                        <div class="text-white text-[12px] bg-red-500 py-[1px] px-[1rem]">
                            2020-2022
                        </div>
                    </div>
                </div>
                <div class="w-[60%] text-left">
                    <div class="font-semibold mb-[2rem]">
                        Certificate of Tester Experience
                    </div>
                    <div class="text-gray-500">
                        I joined the company back in mid 2020 as an Quality Assurance intern and joined as
                        a QA tester focused on manual testing.
                        I learned some work culture, ethics and professionalism along with
                        professional skills culminating to a position as a QA officer.
                    </div>
                </div>
            </div>
        </div>
    </div>
</div>
<Navbar/>
</div> 
</template>

<style scoped>
.main-container{
    width: 100%;
    background: #F0F0F6;
    display: flex;
    padding: 1rem;
    flex-direction: column;
    align-items: center;
    flex-wrap: wrap;
}
/* @media (min-width: 800px){
    .outer-container{
        flex-wrap: nowrap !important;
    }
} */
</style>

<script setup>
import {ref} from 'vue';
//lateral nav
const isActive = ref(false);
const content = ref(1);

const isExpanded= ref(false);

</script>

<template>
    <!-- container -->

    <aside :class="`${isExpanded} ? 'expanded' : '' `">
        <!-- menu toggle wrap -->
        <div class="flex flex-col w-10 h-fit items-center justify-center transition ease-in-out duration-500 ">
            <!-- transition ease-in-out duration-500 -->
            <button @click="isExpanded=!isExpanded" class="flex w-10 h-10 items-center justify-center border-b border-b-gray-700">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-slate-100">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M18.75 19.5l-7.5-7.5 7.5-7.5m-6 15L5.25 12l7.5-7.5" />
                </svg>
            </button>

            


            <div class="flex w-10 h-10 bg-black items-center justify-center border-b border-b-gray-600" @click="content = 2; isActive=true">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-slate-200">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M6.429 9.75L2.25 12l4.179 2.25m0-4.5l5.571 3 5.571-3m-11.142 0L2.25 7.5 12 2.25l9.75 5.25-4.179 2.25m0 0L21.75 12l-4.179 2.25m0 0l4.179 2.25L12 21.75 2.25 16.5l4.179-2.25m11.142 0l-5.571 3-5.571-3" />
                </svg>
            </div>
        </div>

    </aside>


    <div class="absolute flex right-0 top-2/3 transition-transform bg-red-100 p-2" >
        <!-- buttons nav -->
        <div class="flex flex-col ">
            <!-- arrow -->
            <button class="flex w-10 h-10 bg-black items-center justify-center border-b border-b-gray-600" @click="isActive=!isActive; content= 1 ">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-slate-100">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M18.75 19.5l-7.5-7.5 7.5-7.5m-6 15L5.25 12l7.5-7.5" />
                </svg>
            </button>
            <div class="flex w-10 h-10 bg-black items-center justify-center border-b border-b-gray-600" @click="content = 2; isActive=true">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-slate-200">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M6.429 9.75L2.25 12l4.179 2.25m0-4.5l5.571 3 5.571-3m-11.142 0L2.25 7.5 12 2.25l9.75 5.25-4.179 2.25m0 0L21.75 12l-4.179 2.25m0 0l4.179 2.25L12 21.75 2.25 16.5l4.179-2.25m11.142 0l-5.571 3-5.571-3" />
                </svg>
            </div>

            <div class="flex w-10 h-10 bg-black items-center justify-center border-b border-b-gray-500" @click="content=3; isActive=true">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-gray-200">
                    <path stroke-linecap="round" stroke-linejoin="round" d="M12 21a9.004 9.004 0 008.716-6.747M12 21a9.004 9.004 0 01-8.716-6.747M12 21c2.485 0 4.5-4.03 4.5-9S14.485 3 12 3m0 18c-2.485 0-4.5-4.03-4.5-9S9.515 3 12 3m0 0a8.997 8.997 0 017.843 4.582M12 3a8.997 8.997 0 00-7.843 4.582m15.686 0A11.953 11.953 0 0112 10.5c-2.998 0-5.74-1.1-7.843-2.918m15.686 0A8.959 8.959 0 0121 12c0 .778-.099 1.533-.284 2.253m0 0A17.919 17.919 0 0112 16.5c-3.162 0-6.133-.815-8.716-2.247m0 0A9.015 9.015 0 013 12c0-1.605.42-3.113 1.157-4.418" />
                </svg>
            </div>

            <div class="flex w-10 h-10 bg-black items-center justify-center border-b border-b-gray-500" @click="content=4; isActive=true">
                <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-gray-200">
            <path stroke-linecap="round" stroke-linejoin="round" d="M11.42 15.17L17.25 21A2.652 2.652 0 0021 17.25l-5.877-5.877M11.42 15.17l2.496-3.03c.317-.384.74-.626 1.208-.766M11.42 15.17l-4.655 5.653a2.548 2.548 0 11-3.586-3.586l6.837-5.63m5.108-.233c.55-.164 1.163-.188 1.743-.14a4.5 4.5 0 004.486-6.336l-3.276 3.277a3.004 3.004 0 01-2.25-2.25l3.276-3.276a4.5 4.5 0 00-6.336 4.486c.091 1.076-.071 2.264-.904 2.95l-.102.085m-1.745 1.437L5.909 7.5H4.5L2.25 3.75l1.5-1.5L7.5 4.5v1.409l4.26 4.26m-1.745 1.437l1.745-1.437m6.615 8.206L15.75 15.75M4.867 19.125h.008v.008h-.008v-.008z" />
                </svg>
            </div>
        </div>

        <!-- content -->
        
        <div v-if="isActive" class="w-60 flex flex-col justify-center bg-gray-200 relative">
            <!-- heading -->
            <div class="flex justify-center bg-black w-full h-10 items-center text-gray-200 text-base absolute -top-10">Header</div>
            <!-- content 1 -->
            <div v-show="content===1" class="flex items-center justify-center ">
                test content 1
            </div>
            <!-- content 2 -->
            <div v-show="content === 2" class="flex w-60 h-44 items-center justify-center">
                test content 2
            </div>
            <!-- content 3 -->
            <div v-show="content === 3" class="flex w-60 h-52 items-center justify-center">
                test content 3
            </div>
            <!-- content 4 -->
            <div v-show="content === 4" class="flex w-60 h-60 items-center justify-center trans">
                test content 4
            </div>
        </div>
    </div>

    <!-- Original test -->
    <!-- container -->
    <aside :class="`${isExpanded ? 'expanded' : ''}`">
            <!-- menu toggle wrap -->
            <div class="menu-toggle-wrap">
                <!-- menu toggle -->
                <button @click="isExpanded=!isExpanded" class="icon-wrapper">
                    <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M18.75 19.5l-7.5-7.5 7.5-7.5m-6 15L5.25 12l7.5-7.5" />
                    </svg>
                </button>
            </div>

            <!-- content -->
            <div class="content">
                <div class="header">Header</div>
                <div class="flex w-[300px] h-20 items-center justify-center">Content</div>
            </div>
        </aside>

    <!-- tests -->
    <!-- fixed box -->
    <div class="flex absolute right-0 bottom-10 overflow-hidden">
        <!-- movable section -->
        <div class="flex text-gray-600 h-fit  transition ease-out duration-1000 mt-10" :class="`${isExpandedTest ? '-translate-x-0' : 'translate-x-80'}`">
        <!-- translate icons and container x to the right -->
            <div class="flex">
                <div class="menu-toggle-wrap">
                    <!-- arrow toggle -->
                    <button @click="isExpandedTest=!isExpandedTest" class="icon-wrapper">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-gray-300 ">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M18.75 19.5l-7.5-7.5 7.5-7.5m-6 15L5.25 12l7.5-7.5" />
                        </svg>
                    </button>
                    <!-- icon content -->
                    <div class="flex w-10 h-10 bg-black items-center justify-center border-b border-b-gray-600" @click="content = 2; isExpandedTest=true">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-slate-200">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M6.429 9.75L2.25 12l4.179 2.25m0-4.5l5.571 3 5.571-3m-11.142 0L2.25 7.5 12 2.25l9.75 5.25-4.179 2.25m0 0L21.75 12l-4.179 2.25m0 0l4.179 2.25L12 21.75 2.25 16.5l4.179-2.25m11.142 0l-5.571 3-5.571-3" />
                        </svg>
                    </div>
                </div>

                <!-- content -->
                <div class="flex flex-col w-80 bg-gray-300 text-black transition ease-in duration-500 relative">
                    <!-- header -->
                    <div class="flex h-10 w-full items-center justify-center bg-black text-slate-300 absolute -top-10">Header</div>
                    <!-- content -->
                    <div class="flex w-full h-60 items-center justify-center">Content</div>
                </div>
            </div>
        </div>
    </div>

</template>

<style>
aside{
    display: flex;
    flex-direction: column;
    position: absolute;
    right: 0;
    
    background-color: black;
    color: silver;
    width: 2.5rem;
    height: 5rem;
    overflow: hidden;
    transition: 0.5s ease-out;
}

.expanded{
    width: 340px;
    }

.slide-r-to-l-enter-active{
    transition: all 1s ease-out;
}
.slide-r-to-l-leave-active{
    transition: all 1s cubic-bezier(1, 0.5, 0.8, 1);
}
.slide-r-to-l-leave-from,
.slide-r-to-l-enter-to{
    transform: translate(-100%);
}

.slide-r-to-l-enter-from,
.slide-r-to-l-leave-to{
    transform: translate(100%);
}

</style>
<script setup>
import {ref} from 'vue';
import Icon from './Icon.vue'
// import {qTooltip} from 'quasar';

var isExpandedTest= ref(false);
const content = ref(1);

defineProps({
  iconColor: {
    type: String,
    default: "grey"
},
  backgroundColor: {
    type: String,
    default: "black"
},
  positionTop:{
    type: String,
    default: "50%"
  }
})

compatConfig: { MODE: 3 }

</script>

<template>
    <!-- solution 1 -->
    <!-- container, fixed box -->
    <div class="box" >
        <!-- movable section, complete move, buttons and section -->
        <!-- translate icons and container x to the right -->
        <!-- day === "Monday" ? price -= 1.5 : price += 1.5; -->
        <div class="movable-objects" :class="`${isExpandedTest ? 'translate' : 'translate-origin'}`">
                <!-- wrap for all icons -->
                <div class="menu-toggle-wrap group">
                    <!-- arrow toggle -->
                    <button @click="isExpandedTest=!isExpandedTest; (isExpandedTest===false && content!=1) ? content= content : content=1 ;" class="icon-wrapper-fixed">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon-fixed">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M18.75 19.5l-7.5-7.5 7.5-7.5m-6 15L5.25 12l7.5-7.5" />
                        </svg>
                        <!-- <q-tooltip anchor="center left" self="center end">
                            Inicio
                        </q-tooltip> -->
                    </button>

                    <!-- icon content -->
                    <div class="icon-wrapper" @click="content=2; isExpandedTest=true">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="icon">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M6.429 9.75L2.25 12l4.179 2.25m0-4.5l5.571 3 5.571-3m-11.142 0L2.25 7.5 12 2.25l9.75 5.25-4.179 2.25m0 0L21.75 12l-4.179 2.25m0 0l4.179 2.25L12 21.75 2.25 16.5l4.179-2.25m11.142 0l-5.571 3-5.571-3" />
                        </svg>
                    </div>

                    <!-- try slot -->
                    <Icon title="Map Legend" >
                        <!-- background-color="rgb(51 65 85)" icon-color="black" -->
                        <!-- icon-color background-color -->
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-gray-300">
                            <path stroke-linecap="round" stroke-linejoin="round" d="M12 21a9.004 9.004 0 008.716-6.747M12 21a9.004 9.004 0 01-8.716-6.747M12 21c2.485 0 4.5-4.03 4.5-9S14.485 3 12 3m0 18c-2.485 0-4.5-4.03-4.5-9S9.515 3 12 3m0 0a8.997 8.997 0 017.843 4.582M12 3a8.997 8.997 0 00-7.843 4.582m15.686 0A11.953 11.953 0 0112 10.5c-2.998 0-5.74-1.1-7.843-2.918m15.686 0A8.959 8.959 0 0121 12c0 .778-.099 1.533-.284 2.253m0 0A17.919 17.919 0 0112 16.5c-3.162 0-6.133-.815-8.716-2.247m0 0A9.015 9.015 0 013 12c0-1.605.42-3.113 1.157-4.418" />
                        </svg>
                    </Icon>

                    <div class="icon-wrapper" @click="content=4; isExpandedTest=true">
                        <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 24 24" stroke-width="1.5" stroke="currentColor" class="w-6 h-6 text-gray-200">
                        <path stroke-linecap="round" stroke-linejoin="round" d="M11.42 15.17L17.25 21A2.652 2.652 0 0021 17.25l-5.877-5.877M11.42 15.17l2.496-3.03c.317-.384.74-.626 1.208-.766M11.42 15.17l-4.655 5.653a2.548 2.548 0 11-3.586-3.586l6.837-5.63m5.108-.233c.55-.164 1.163-.188 1.743-.14a4.5 4.5 0 004.486-6.336l-3.276 3.277a3.004 3.004 0 01-2.25-2.25l3.276-3.276a4.5 4.5 0 00-6.336 4.486c.091 1.076-.071 2.264-.904 2.95l-.102.085m-1.745 1.437L5.909 7.5H4.5L2.25 3.75l1.5-1.5L7.5 4.5v1.409l4.26 4.26m-1.745 1.437l1.745-1.437m6.615 8.206L15.75 15.75M4.867 19.125h.008v.008h-.008v-.008z" />
                        </svg>
                    </div>

                </div>

                <!-- content -->
                <div class="content-wrapper">
                    <!-- header -->
                    <div class="title">Header</div>
                    <!-- content -->
                    <div class="flex w-full h-60 items-center justify-center bg-gray-200">
                        <!-- content 1 -->
                        <div v-show="content === 1" class="flex w-full items-center justify-center ">
                            Select one option from the menu
                        </div>
                        <!-- content 2 -->
                        <div v-show="content === 2" class="flex w-full h-80 items-center justify-center ">
                            content 1
                        </div>

                        <div v-show="content === 3" class="flex w-full h-80 items-center justify-center ">
                            content 2
                        </div>

                        <div v-show="content === 4" class="flex w-full h-44 items-center justify-center ">
                            content 3
                        </div>
                    </div>
                </div>
        </div>
    </div>
</template>

<style scoped>
/* flex absolute right-0 bottom-10 overflow-hidden */
.box{
    --var-translate-x: 300px;
    display: flex;
    position: absolute;
    width: fit-content;
    right: 0px;
    /* prop */
    top: v-bind(positionTop);
    overflow: hidden;
    transition: 0.8s ease-out ;
    /* transform: translate(--var-translate-x); */
}
.translate{
    transition: 0.8s ease-out ;
    transform: translate(0px);
}

.translate-origin{
    transition: 0.8s ease-out;
    transform: translate(320px);
}

/* flex relative text-gray-600 h-fit  transition ease-out duration-1000 mt-10 */
.movable-objects{
    --var-translate-x: 300px; /* can change according the width of the container */
    display: flex;
    position: relative;
    color: rgb(75 85 99); /* this color will be props */
    height: fit-content;
    transition: 0.8s ease-out ;
    transform: translate(--var-translate-x);
}

.menu-toggle-wrap {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    /* prop to change */
    background-color: v-bind(backgroundColor); 
    height: fit-content;
    /* margin-bottom: 1rem; */
    /* prop to change*/
    color: rgb(209 213 219); 
    position: relative;
    top: 0px;
    transition: 0.5s ease-in-out;
    margin-top: 40px;
}
.icon-wrapper-fixed{
    display: flex;
    width: 40px;
    height: 40px;
    /* change prop */
    background-color: v-bind(backgroundColor); 
    align-items: center;
    justify-content: center;
    border-bottom-width: 1px;
    border-bottom-color: rgb(55 65 81);
}
.icon-wrapper{
    display: flex;
    width: 40px;
    height: 40px;
    /* change prop */
    /* background-color: black; */
    align-items: center;
    justify-content: center;
    border-bottom-width: 1px;
    border-bottom-color: rgb(55 65 81);
}

.icon-fixed{
    /* font-size: 2rem;  */
    width: 25px;
    height: 25px;
    color: rgb(203 213 225); /* icon color */
    transition: 0.5s ease-out;
}
.icon-fixed:hover{
        color: aqua;
        transform: translate(-0.5rem);
    }

.translate .icon-wrapper-fixed{
    transform: rotate(-180deg);
}
.icon{
    /* font-size: 2rem;  */
    width: 24px;
    height: 24px;
    color: rgb(203 213 225); /* icon color */
    transition: 1s ease-out;
}

/* flex flex-col w-80 bg-gray-300 text-black transition ease-in duration-500 relative */
.content-wrapper{
    display: flex;
    flex-direction: column;
    width: 320px;
    background-color: rgb(229 231 235); /* color change */
    color: black;
    position: relative;
    margin-top: 40px;
}
.title{
    display: flex;
    height: 40px;
    width: 100%;
    align-items: center;
    justify-content: center;
    background-color: v-bind(backgroundColor);
    position: absolute;
    top: -40px;
    color: gray;
}

/* .inner-content{

} */

/* test */
/* aside{
    display: flex;
    color: silver;
    width: 40px;
    height: fit-content;
    overflow: hidden;
    transition: 0.8s ease-out;
} */

</style>
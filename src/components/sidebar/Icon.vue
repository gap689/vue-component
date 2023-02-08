<script setup>
// const props = defineProps(['title', ])

defineProps({
  title: {
    type: String,
    required: true
},
//   iconColor: {
//     type: String,
//     default: "grey"
// },
//   backgroundColor: {
//     type: String,
//     default: "black"
// }
})
</script>

<template>
    <div class="icon-wrapper" @click="content = 3; isExpandedTest=true">
        <slot></slot>
    </div>
</template>

<style scoped>
.icon-wrapper{
    display: flex;
    width: 40px;
    height: 40px;
    /* change prop */
    /* background-color: v-bind(backgroundColor);  */
    color: v-bind(iconColor); /* change prop */
    align-items: center;
    justify-content: center;
    border-bottom-width: 1px;
    border-bottom-color: rgb(55 65 81);
}
</style>
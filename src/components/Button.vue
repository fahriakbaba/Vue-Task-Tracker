<template>
    <button v-on:click="clickBtn" :style="{backgroundColor: bgColor}">{{text}}</button>
</template>

<script>
export default {
    name: "Button",
    props: {
        text: String,
        bgColor: String
    },
    methods: {
        clickBtn: () => console.log("btn is clicked"),
    }
} 
</script>

<style scoped>
</style>
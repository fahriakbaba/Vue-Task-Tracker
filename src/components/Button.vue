<template>
    <button v-on:click="$emit('toggle-btn')" :style="{backgroundColor: bgColor}">{{text}}</button>
</template>

<script>
export default {
    name: "Button",
    props: {
        text: String,
        bgColor: String
    },
} 
</script>

<style scoped>
button {
    padding: .3rem .5rem;
    cursor: pointer;
    border-radius: 3px;
    outline:none;
    color: white;
    border: none;
    font-size: .7rem;
}
 
</style>
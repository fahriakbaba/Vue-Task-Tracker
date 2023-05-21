<template>
    <ul :key="todo.id" class="todos" v-for="todo in todos">
       {{ todo.title }}
    </ul>
</template>

<script>


export default {
    name: "Tasks",
    props: ["todos"],

}
</script>

<style scoped>
 
</style>
<template>
    <ul>
        <li :key="todo.id" v-for="todo in todos" v-on:dblclick="toggleClick(todo.id)">
            <Task :todo="todo" @delete-task="$emit('delete-task', todo.id)"/>
        </li>
    </ul>
</template>

<script>
import Task from "./Task.vue";

export default {
    name: "Tasks",
    components: {
        Task,
    },
    props: {
        todos: Array,
    },
    emits: ["delete-task"],
    methods: {
        toggleClick (id){
            this.$emit("toggle-task", id);
        }
    }
}
</script>

<style scoped>
ul {
    list-style-type: none;
}
</style>
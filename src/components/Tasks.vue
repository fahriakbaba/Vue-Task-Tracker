<template>
    <ul>
        <li :key="todo.id" v-for="todo in todos">
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
    emits: ["delete-task",]
}
</script>

<style scoped>
ul {
    list-style-type: none;
}
</style>
<template>
    <ul class="todos">
        <li :key="todo.id" v-for="todo in todos">
            <Task :todo="todo" />
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

}
</script>

<style scoped></style>
<template>
    <li>
        {{ todo.title }}
    </li>
</template>

<script>
export default {
    name: "Task",
    props: {
        todo: Object
    },
    methods: {

    },
    created() {
        console.log(this.todo);
    }
}
</script>

<style scoped></style>
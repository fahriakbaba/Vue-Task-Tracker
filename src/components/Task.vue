<template>
    <li>
        <h5>{{ todo.title }}</h5>
        <p>{{ todo.day }}</p>
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

<style scoped>
 
</style>
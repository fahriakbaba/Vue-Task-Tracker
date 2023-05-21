<template>
    <header>
        <h3>Task Tracker</h3>
        <Button :text="text" :bgColor="bgColor" />
    </header>
</template>

<script>
import Button from "./Button.vue";

export default {
    name: "Header",
    data: () => ({
        text: "Add Task",
        bgColor: "green",
    }),
    components: {
        Button,
    }
}
</script>

<style>
</style>
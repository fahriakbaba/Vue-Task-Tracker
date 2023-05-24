<template>
    <header>
        <h3>Task Tracker</h3>
        <Button :text="showTask ? 'Close' : 'Add Task' " :bgColor="`${showTask ? '#DC3545' : 'green'}`" @toggle-btn="$emit('toggle-btn')" />
    </header>
</template>

<script>
import Button from "./Button.vue";

export default {
    name: "Header",
    props: {
        showTask: Boolean,
    },
    components: {
        Button,
    },
    emits: ["toggle-btn"],
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 1rem;
}

header h3 {
    letter-spacing: .7px;
}
</style>
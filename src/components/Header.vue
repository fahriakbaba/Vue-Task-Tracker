<template>
    <header>
        <h3>Task Tracker</h3>
        <Button :text="showTask ? 'Add Task' : 'Close' " :bgColor="`${showTask ? 'green' : 'darkred'}`" />
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
    }
}
</script>

<style scoped>
header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: .75rem;
}

header h3 {
    letter-spacing: .7px;
}
</style>
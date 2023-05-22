<template>
    <form class="form">
        <div class="form-group">
            <label for="task">Task</label>
            <input id="task" type="text" placeholder="Add Task" />
        </div>
        <div class="form-group">
            <label for="dayAndTime">Day & Time</label>
            <input id="dayAndTask" type="text" placeholder="Add Day & Time" />
        </div>
        <div class="form-reminder">
            <label for="reminder">Set Reminder</label>
            <input type="checkbox" name="reminder" id="reminder">
        </div>
        <button type="submit">Save Task</button>
    </form>
</template>

<script>
export default {
    name: "AddTask",
}
</script>

<style scoped>
.form {
    display: flex;
    flex-direction: column;
    justify-content: center;
    padding: .2rem;
    margin-bottom: .75rem;
}

.form-group {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
}
</style>
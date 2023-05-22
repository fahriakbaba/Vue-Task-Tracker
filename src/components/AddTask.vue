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
    margin-top: .75rem;
}

.form-group label {
    font-size: .85rem;
    font-weight: 600; 
    margin-bottom: .25rem;  
    letter-spacing: .5px;
}

.form-group input {
    width: 100%;
    border-radius: 3px;
    padding: .3rem .6rem;
    transition: border .3s;
    outline: none;
    border: 2px solid gray;
}

.form-group input:focus {
    border: 2px solid rgba(28, 28, 214, 0.774);
}

.form-reminder {
    display: flex;
    gap: 7rem;
    align-items: center;
    margin-top: .75rem;
    font-size: .85rem;
    font-weight: 600; 
}

.form-reminder input {
    cursor: pointer;
}

button {
    margin-top: .75rem;
    padding: .3rem .6rem;
    background-color: black;
    color: white;
    border-radius: 3px;
    cursor: pointer;
}
</style>
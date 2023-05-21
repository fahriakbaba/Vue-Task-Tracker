<template>
    <div :class="`${todo.isDone && 'border-left'}`">
        <h5>{{ todo.title }}
            <i class="fa-solid fa-trash icon" v-on:click="$emit('delete-task', todo.id)"></i>
        </h5>
        <p>{{ todo.day }}</p>
    </div>
</template>

<script>
export default {
    name: "Task",
    props: {
        todo: Object
    },
    methods: {

    },
}
</script>

<style scoped>
div{
    margin: .3rem 0;
    background-color: whitesmoke;
    padding: .5rem;
}

div h5 {
    font-size: .8rem;
    font-weight: 600;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

div p {
    font-size: .7rem;
    color: rgb(73, 69, 69);
}

.icon {
    color: #DC3545;
    cursor: pointer;
}

.border-left {
    border-left: 4px solid green;
}
</style>
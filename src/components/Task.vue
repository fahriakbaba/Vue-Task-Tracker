<template>
    <li>
        <h5>{{ todo.title }}
            <i class="fa-solid fa-trash icon"></i>
        </h5>
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
li {
    margin: .3rem 0;
}

li h5 {
    font-size: .8rem;
    font-weight: 600;
    display: flex;
    justify-content: space-between;
    align-items: center;
}

li p {
    font-size: .7rem;
    color: rgb(73, 69, 69);
}

.icon {
    color: rgb(121, 7, 7);
    cursor: pointer;
}
</style>
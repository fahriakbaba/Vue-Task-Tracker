<template>
  <div class="container">
    <Header />
    <Tasks :todos="todos" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
  },
  data() {
    return {
      todos: [
        {id:1, title: "Drink a couple of  milk", day:"Friday"},
        {id:2, title: "Ride a bike", day:"Tuesday"},
        {id:3, title: "Go shopping", day:"Monday"}
      ],
    }
  },
  methods: {
    deleteMessage(msg) {
      console.log(msg);
      console.log("todos: ", this.todos);
    }
  },
  // async mounted() {
  //   const res = await fetch("https://jsonplaceholder.typicode.com/todos");
  //   const data = await res.json();
  //   this.todos = data; 
  // }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins&display=swap');

*{
  padding: 0;
  margin: 0;
  box-sizing: border-box;
  font-family: 'Poppins', sans-serif;
}

.container {
  border: 2px solid rgba(0, 45, 128, 0.308);
  padding: 1.5rem;
  border-radius: 4px;
  display: flex;
  flex-direction: column;
  width: 30%;
  margin:  3rem auto;
}
</style>

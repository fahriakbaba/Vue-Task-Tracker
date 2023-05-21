<template>
  <div class="container">
    <Header />
    <Tasks todos="todos" />
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
      todos: [],
    }
  },
  methods: {
    deleteMessage(msg) {
      console.log(msg);
      console.log("todos: ", this.todos);
    }
  },
  async mounted() {
    const res = await fetch("https://jsonplaceholder.typicode.com/todos");
    const data = await res.json();
    this.todos = data; 
  }
}
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
</style>

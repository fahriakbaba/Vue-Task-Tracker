<template>
  <div class="container">
    <Header />
  </div>
</template>

<script>
import Header from "./components/Header.vue";

export default {
  name: 'App',
  components: {
    Header,
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

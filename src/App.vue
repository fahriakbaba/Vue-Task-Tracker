<template>
  <div class="container">
    <Header :showTask="showTask" @toggle-btn="toggleBtn" />
    <div v-show="showTask">
      <AddTask @add-task="handleAddTask" />
    </div>
    <Tasks :todos="todos" @delete-task="deleteTask" @toggle-task="updatedTask" />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue";

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask,
  },
  data() {
    return {
      todos: [
        { id: 1, title: "Drink a couple of  milk", day: "Friday", isDone: false },
        { id: 2, title: "Ride a bike", day: "Tuesday", isDone: true },
        { id: 3, title: "Go shopping", day: "Monday", isDone: true }
      ],
      showTask: true,
    }
  },
  methods: {
    deleteTask(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    updatedTask(id) {
      this.todos = this.todos.map(todo => todo.id === id ? {...todo, isDone: !todo.isDone} : todo)
    },
    handleAddTask(newTask) {
      //first option for adding new task
      // this.todos.push(newTask);
      //second option for adding new task
      this.todos = [...this.todos, newTask];
    },
    toggleBtn() {
      this.showTask = !this.showTask;
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

* {
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
  min-width: 425px;
  width: 30%;
  margin: 3rem auto;
}
</style>

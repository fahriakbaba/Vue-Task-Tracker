<template>
  <div class="container" v-cloak="cloak">
    <Header :showTask="showTask" @toggle-btn="toggleBtn" />
    <div v-show="showTask">
      <AddTask @add-task="handleAddTask" />
    </div>
    <Tasks :todos="todos" @delete-task="deleteTask" @toggle-task="updatedTask" />
    <Footer />
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import Tasks from "./components/Tasks.vue";
import AddTask from "./components/AddTask.vue";
import Footer from "./components/Footer.vue";

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask,
    Footer,
  },
  data() {
    return {
      todos: [],
      showTask: true,
    }
  },
  methods: {
    async deleteTask(id) {
      await fetch("http://localhost:8888/todos/" + id, { method: "DELETE"});
      this.todos = this.todos.filter(todo => todo.id !== id);
      console.log("Delete task: ", id);
    },
    
    async updatedTask(id) {
      const taskFS = await fetch("http://localhost:8888/todos/" + id);
      const taskFSJSON = await taskFS.json();
      const updTask = {
        ...taskFSJSON,
        isDone: !taskFSJSON.isDone
      };

      const res = await fetch("http://localhost:8888/todos/" + id, {
        method: "PUT",
        headers: {
          'Content-type': 'application/json; charset=UTF-8',
        },
        body: JSON.stringify(updTask)
      });
      const data = await res.json();

      this.todos = this.todos.map(todo => todo.id === id ? { ...todo, isDone: data.isDone } : todo);
      console.log("Updated task: ", id);
    },

    async handleAddTask(newTask) {
      const res = await fetch("http://localhost:8888/todos", {
        method: 'POST',
        body: JSON.stringify(newTask),
        headers: {
          'Content-type': 'application/json; charset=UTF-8',
        },
      });
      const data = await res.json();
      this.todos = [...this.todos, data];
      console.log("Add task: ", newTask);
    },

  toggleBtn() {
      this.showTask = !this.showTask;
    }
  },
  async mounted() {
    const res = await fetch("http://localhost:8888/todos");
    const data = await res.json();
    this.todos = data;
  }
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

[cloak] {
  display: none;
}

@media (max-width: 480px) {
  body {
    display: flex;
    justify-content: center;
    align-items: center;
  }

  .container {
    margin: 3rem .5rem;
    min-width: 375px;
  }
}
</style>

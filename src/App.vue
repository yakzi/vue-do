<template>
<div class="container">
  <Header title="VueDo - ToDo List made with Vue.JS"/>
  <TodoViewer @delete-todo="deleteTodo" :todos="todos" />
  </div>
</template>

<script>
import Header from './components/Header'
import TodoViewer from './components/TodoViewer.vue' 

export default {
  name: 'App',
  components: {
    Header,
    TodoViewer
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {
      if(confirm('Are you sure?')){
      this.todos = this.todos.filter((todo) => todo.id !== id)
    }
    }
  },
  created() {
    this.todos = [
      {
        id: 1,
        text: 'Buy new car',
        priority: 'High'
      },
      {
        id: 2,
        text: 'Sell old phone',
        priority: 'Medium'
      },
      {
        id: 3,
        text: 'Pick up new doors',
        priority: 'High'
      }
    ]
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

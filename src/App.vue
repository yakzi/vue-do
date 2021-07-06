<template>
<div class="container">
  <Header title="VueDo - ToDo List made with Vue.JS"/>
  <TodoAdder @add-todo="addTodo"/>
  <TodoViewer @delete-todo="deleteTodo" :todos="todos" />
  </div>
</template>

<script>
import Header from './components/Header'
import TodoViewer from './components/TodoViewer' 
import TodoAdder from './components/TodoAdder'
export default {
  name: 'App',
  components: {
    Header,
    TodoViewer,
    TodoAdder
  },
  data() {
    return {
      todos: []
    }
  },
  methods: {
    deleteTodo(id) {
      this.todos = this.todos.filter((todo) => todo.id !== id)
    },
    addTodo(todo){
      this.todos = [...this.todos, todo]
    }
  },
  created() {
    this.todos = [
      
    ]
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Encode+Sans+SC:wght@200&display=swap');
* {
  box-sizing: border-box;
}
body {
  font-family: 'Encode Sans SC', sans-serif;
}
.container {
  max-width: 500px;
  margin: 20px auto;
  min-height: 300px;
  border: 1px solid black;
  padding: 20px;
  border-radius: 10px;
}
.btn {
  background: rgb(221, 221, 221);
  color: black;
  border: 1px solid black;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
  font-size: 15px;
  margin-bottom: 10px;
  width: 50%;
  box-shadow: 0 0 2px 2px greenyellow;
}
.btn:active {
  transform: scale(0.98);
}
</style>

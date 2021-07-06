<template> 
<div :key="todo.id" v-for="todo in todos">
    <Todo @delete-todo="$emit('delete-todo', todo.id)" :todo="todo"/>

</div>

</template>

<script>
import Todo from './Todo'
export default {
    name: 'TodoViewer',
    props: {
         todos: Array
    },
    components: {
        Todo
    },
    emits: ['delete-todo'],
}
</script>
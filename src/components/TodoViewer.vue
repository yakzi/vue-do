<template> 
<div v-for="todo in todos">
    <h3> {{ todo.text }}</h3>

</div>

</template>

<script>
    export default {
        name: 'TodoViewer',
        props: {
            todos: Array
        }
    }
</script>
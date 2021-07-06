<template>
<div class="todo">
    <h3 @click="onDone(todo.id)">{{ todo.text }}</h3>
    <i @click="onDelete(todo.id)" class="fas fa-times"></i>
    <p>{{ todo.priority }}</p>
</div>

</template>

<script> 
export default{
    name: 'Todo',
    props: {
        todo: Object
    },
    methods: {
        onDelete(id) {
            this.$emit('delete-todo', id)
        },
        onDone(id) {
            
        }
    }
}
</script>

<style scope> 

.todo {
    background: lightblue;
    text-align: left;
    padding-left: 5px;
}

.todo p{
    font-style: italic;
}

.fas {
    color: red;
}

</style>
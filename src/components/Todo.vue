<template>
<div class="todo">
    <i @click="$emit('delete-todo', id)" id="todoX" class="fas fa-times"></i>
    <h3 @click="onDone(todo.id)">{{ todo.text }}</h3>
    <p>{{ todo.priority }}</p>
</div>

</template>

<script> 
export default{
    name: 'Todo',
    props: {
        todo: Object
    },
}
</script>

<style scope> 

.todo {
    border: 1px solid black;
    text-align: left;
    padding-left: 5px;
    margin-top: 10px;
    border-radius: 5px;
    margin-bottom: 5px;
    padding-bottom: 10px;
    box-shadow: 0 0 2px 2px lightblue;
}

.todo p{
    margin-top: 10px;
    font-style: italic;
}

.todo #todoX{
    float: right;
    margin-right: 10px;
    margin-top: 5px;
}

.fas {
    color: red;
}

</style>
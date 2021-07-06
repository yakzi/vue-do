<template>
<div class="todo">
    <h3>{{ todo.text }}</h3>
    <p>{{ todo.priority }}</p>
</div>

</template>

<script> 
export default{
    name: 'Todo',
    props: {
        todo: Object
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
    color: lightcoral;
}

</style>
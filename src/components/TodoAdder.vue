<template>
  <form @submit="onAdd" class="add-form">
    <div class="form-control">
      <label>Todo task</label>
      <input type="text" v-model="text" name="text" placeholder="Add Task" />
    </div>
    <div class="form-control">
      <input type="text" v-model="priority" name="text" placeholder="Enter priority"/>
    </div>
    <div class="form-control">
      <input type="submit" value="Save ToDo" class="btn btn-block" />
    </div>
  </form>
</template>

<script> 
export default {
    name: 'AddTodo',
    data(){
        return{
            text: '',
            priority: ''
        }
    },
    methods: {
        onAdd(e) {
            e.preventDefault()
            if(!this.text) {
                alert('Please add a task')
                return
            }

            const newTodo = {
                id: Math.floor(Math.random() * 1234),
                text: this.text,
                priority: this.priority
            }

            console.log(newTodo)
            this.text = ''
            this.priority = ''
        }
    }
}
</script>

<style scoped>
</style>

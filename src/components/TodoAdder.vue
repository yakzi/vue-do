<template>
  <form @submit="onAdd" class="add-form">
    <div class="form-control">
      <b>Add new ToDo</b> <br>
      <input type="text" id="inputT" v-model="text" name="text" placeholder="Enter todo name" />
    </div>
    <div class="form-control">
      <input type="text" id="inputT" v-model="priority" name="text" placeholder="Enter priority"/>
    </div>
    <div class="form-control">
      <input type="submit" id="inputB" value="Add" class="btn btn-block" />
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
                alert('Please add ToDo name')
                return
            }

            const newTodo = {
                id: Math.floor(Math.random() * 1234),
                text: this.text,
                priority: this.priority
            }

            this.$emit('add-todo', newTodo)
            this.text = ''
            this.priority = ''
        }
    }
}
</script>

<style scoped>
.add-form{
  text-align: center;
  border: 1px solid rgb(138, 138, 138);
  margin: 10px;
}
.add-form #inputT{
  margin: 10px;
  text-align: center;
}

.add-form #inputB{
  text-align: center;
}
</style>

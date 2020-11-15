<template>
  <div>
    <form @submit="wristslap">
      <input type="text" v-model="title" name="title" placeholder="Add a todo">
      <input class="btn" type="submit" value="Submit" >
    </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid'
export default {
  name: "AddTodo",
  data() {
    return {
      title: ''
    }
  },
  methods: {
    wristslap() {
      event.preventDefault()
      const newTodo = {
        id: uuidv4(),
        title: this.title,
        completed: false
      }
      // send up to parent
      this.$emit("add-todo", newTodo)
      // console.log("submitted a todo")
      // console.log(newTodo)
    }
  }
}
</script>

<style scoped>
  form {
    display: flex;
  }
  input[type="text"] {
    flex: 10;
    padding: 5px;
  }
  input[type="submit"] {
    flex: 2;
  }
  
</style>
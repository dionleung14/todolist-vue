<template>
  <div>
    <form @submit="wristslap">
      <input type="text" v-model="autumn" name="autumn" placeholder="Add a todo">
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
      autumn: ''
    }
  },
  methods: {
    wristslap(event) {
      event.preventDefault()
      const newTodo = {
        id: uuidv4(),
        title: this.autumn,
        completed: false
      }
      // send up to parent
      this.$emit("add-todo", newTodo);
      this.autumn = ""
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
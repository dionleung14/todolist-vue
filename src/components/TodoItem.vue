<template>
  <div class="todo-item" v-bind:class="{'is-complete':coffee.completed}">
    <p>
      <input type="checkbox" v-on:change="markComplete">
      Todo id: {{ coffee.id }}
      Name: {{ coffee.title }}
      Completed: {{ coffee.completed }} 
    <button class="del" :id="coffee.id" v-on:click="deleteMe" @click="$emit('del-todo', coffee.id)">X</button>
    </p>
  </div>
</template>

<script>
  export default {
    name: "TodoItem",
    props: ["coffee"],
    methods: {
      markComplete() {
        this.coffee.completed = !this.coffee.completed
      },
      deleteMe() {
        // console.log("i've been clicked!")
        // console.log(this.coffee.id)
      }
    }
  }
</script>

<style scoped>
  .todo-item {
    background: #f4f4f4;
    padding: 10px;
    border-bottom: 1px #ccc dotted;
  }

  .is-complete {
    text-decoration: line-through;
  }

  .del {
    background: #ff0000;
    color: #fff;
    border: none;
    padding: 5px 9px;
    border-radius: 50%;
    cursor: pointer;
    float: right
  }
</style>
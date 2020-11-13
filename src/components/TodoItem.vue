<template>
  <div class="todo-item" v-bind:class="{'is-complete':coffee.completed}">
    <p>Todo id: {{ coffee.id }} </p>
    <h1>Name: {{ coffee.title }} </h1>
    <h1> Completed: {{ coffee.completed }} </h1>
    <button :id="coffee.id">Complete</button>
  </div>
</template>

<script>
export default {
  name: "TodoItem",
  props: ["coffee"]
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
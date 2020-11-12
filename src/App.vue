<template>
  <div id="app">
    {{msg}}
    <Todos v-bind:geoduck="todosArr" />
  </div>
</template>

<script>
import Todos from "./components/Todos.vue";
  export default {
    name: "App",
    components: {
      Todos: Todos
    },
    data() {
      return {
        msg: "Hello",
        todosArr: [
          {
            id: 1,
            title: "todo uno",
            completed: false
          },
          {
            id: 2,
            title: "todo two",
            completed: false
          },
          {
            id: 3,
            title: "todo three",
            completed: true
          },
        ]
      }
    }
  };
</script>

<style>
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
  }
</style>

<template>
  <div id="app">
    {{msg}}
  </div>
</template>

<script>
  export default {
    name: "App",
    components: {
    },
    data() {
      return {
        msg: "Hello",
        todos: [
          {
            id: 1,
            title: "todo one",
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

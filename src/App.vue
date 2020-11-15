<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="aWholeNewTodo"/>
    <Todos v-bind:geoduck="todosArr" v-on:rec-one-todo="removeTodo" />
    {{ msg }}
  </div>
</template>

<script>
  import Todos from "./components/Todos.vue";
  import AddTodo from "./components/AddTodo.vue";
  import Header from "./components/layout/Header.vue";
  export default {
    name: "App",
    components: {
      Todos: Todos,
      Header,
      AddTodo
    },
    methods: {
      removeTodo(id) {
        console.log("received in app.vue");
        console.log(id);
        this.todosArr = this.todosArr.filter(item => (item.id !== id));
      },
      aWholeNewTodo(data) {
        console.log("a new todo was received")
        console.log(data)
      }
    },
    data() {
      return {
        msg: "Hello",
        todosArr: [
          {
            id: 1,
            title: "todo uno",
            completed: false,
          },
          {
            id: 2,
            title: "todo two",
            completed: false,
          },
          {
            id: 3,
            title: "todo three",
            completed: true,
          },
        ],
      };
    },
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

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: #fff;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666
  }
</style>

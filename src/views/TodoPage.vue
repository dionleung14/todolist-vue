<template>
  <div id="app">
    <!-- <Heade r /> -->
    <AddTodo v-on:add-todo="aWholeNew" />
    <Todos v-bind:geoduck="todosArr" v-on:rec-one-todo="removeTodo" />
    {{ msg }}
  </div>
</template>

<script>
  import Todos from "../components/Todos.vue";
  import AddTodo from "../components/AddTodo.vue";
  // import Header from "../components/layout/Header.vue";
  export default {
    name: "App",
    components: {
      Todos: Todos,
      // Header,
      AddTodo,
    },
    data() {
      return {
        msg: "Hello",
        todosArr: [
          // {
          //   id: 1,
          //   title: "todo uno",
          //   completed: false,
          // },
          // {
          //   id: 2,
          //   title: "todo two",
          //   completed: false,
          // },
          // {
          //   id: 3,
          //   title: "todo three",
          //   completed: true,
          // },
        ],
      };
    },
    created() {
      // console.log("yeeeeeet");
      fetch("https://jsonplaceholder.typicode.com/users/1/todos?_limit=5")
        .then(
          response =>
            // console.log(response.json());
            // console.log("hello");
            response.json()
          // console.log(data);
        )
        .then(json => {
          json.forEach(element => {
            // console.log("oi oi oi");
            // console.log(element);
            // this.percocet();
            this.todosArr = [...this.todosArr, element];
            // this.todosArr.push(element)
          });
          // this.todosArr = json
        })
        .catch(err => console.log(err));
    },
    methods: {
      removeTodo(id) {
        fetch(`https://jsonplaceholder.typicode.com/todos/${id}`, {
          method: "DELETE",
        })
        .then(this.todosArr = this.todosArr.filter(item => item.id !== id))
        .catch(err => console.log(err))
        // console.log("received in app.vue");
        // console.log(id);
        // this.todosArr = this.todosArr.filter(item => item.id !== id);
      },
      aWholeNew(data) {
        const { title, completed } = data;
        fetch("https://jsonplaceholder.typicode.com/todos", {
          method: "POST",
          body: JSON.stringify({
            title,
            completed,
          }),
        })
          .then(response => {
          console.log(response.body);
          response.json();
          (this.todosArr = [...this.todosArr, response])
          })
          .then(json => {
            console.log(json);
          // (this.todosArr = [...this.todosArr, json])
            })
          .catch(err => console.log(err));
        // this.todosArr.push(data)
        // console.log("a new todo was received")
        // console.log(data)
      },
      percocet() {
        console.log("percocet");
      },
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
    background: #666;
  }
</style>

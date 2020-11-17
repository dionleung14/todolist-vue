<template>
  <div>
    <div v-for="pokemon in geoduck" v-bind:key="pokemon.id">
      <!-- <h3>{{ pokemon.title }}</h3> -->
      <TodoItem v-bind:coffee="pokemon" v-on:del-todo="$emit('rec-one-todo', pokemon.id)"/>
    </div>
  </div>
</template>

<script>
  import TodoItem from './TodoItem.vue'

  export default {
    name: "Todos",
    components: {
      TodoItem
    },
    props: ["geoduck"],
    methods: {
      received() {
        console.log("received a payload")
      },
    }
  };
</script>

<style scoped>
</style>

<template>
  <div>
    <div v-for="pokemon in geoduck" v-bind:key="pokemon.id">
      <h3>{{ pokemon.title }}</h3>
      <TodoItem v-bind:todo="pokemon"/>
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
    props: ["geoduck"]
  };
</script>

<style scoped>
</style>

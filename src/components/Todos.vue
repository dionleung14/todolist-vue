<template>
  <div>
    <div v-for="pokemon in listTodos" v-bind:key="pokemon.id">
      <h3>{{ pokemon.title }}</h3>
    <TodoItem />
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
    props: ["listTodos"]
  };
</script>

<style scoped>
</style>

<template>
  <div>
    <div v-for="pokemon in listTodos" v-bind:key="pokemon.id">
      <h3>{{ pokemon.title }}</h3>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Todos",
    props: ["listTodos"]
  };
</script>

<style scoped>
</style>

<template>
  <div>
    <div v-for="listitem in todos" v-bind:key="listitem">
      <h3>{{ listitem.title }}</h3>
    </div>
  </div>
</template>

<script>
  export default {
    name: "Todos",
    props: ["todos"]
  };
</script>

<style scoped>
</style>

<script setup lang="ts">
const message = "Hello from my new component!"
const openReadmeInEditor = () => fetch('/__open-in-editor?file=README.md')
</script>

<template>
  <div class="my-component">
    <h1>{{ message }}</h1>
  </div>
</template>
<style scoped>
/* Styles specific to this component */
h1 { color: #42b983; }
</style>
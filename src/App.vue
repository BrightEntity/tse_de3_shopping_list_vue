<template>
  <div id="app">
    <h1>Ma Shopping List</h1>
    <ShoppingList />
  </div>
</template>

<script>
import ShoppingList from "./components/ShoppingList";

export default {
  name: 'App',
  components: {
    ShoppingList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

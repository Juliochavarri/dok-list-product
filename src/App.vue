<template>
  <div id="app">
    <ListItems />
  </div>
</template>

<script>
import ListItems from './components/ListItems.vue'

export default {
  name: 'App',
  components: {
    ListItems
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

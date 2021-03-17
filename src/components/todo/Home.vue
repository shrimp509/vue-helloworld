<template>
  <div id="app">
    <TodoList :things="things"/>
  </div>
</template>

<script>
import TodoList from './TodoList.vue'

export default {
  name: 'Home',
  components: {
    TodoList
  },
  data() {
    return {
      things: ['First thing', 'Second todo']
    }
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

TodoList {
  text-align: center;
}
</style>

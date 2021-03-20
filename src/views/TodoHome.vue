<template>
  <div id="app">
    <TodoList id="todo_list" :things="things"/>
  </div>
</template>

<script>
import TodoList from '../components/todo/TodoList.vue'

export default {
  name: 'Home',
  components: {
    TodoList
  },
  data() {
    return {
      things: [
        { content: 'First thing', checked: true },
        { content: 'Second todo', checked: false }
      ]
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

</style>

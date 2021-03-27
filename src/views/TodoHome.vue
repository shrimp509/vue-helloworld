<template>
<div id="app">
  <TodoList v-for="list in todoLists" :key="list.list_name" :todoList="list" class="relative-sidebar" />
</div>
</template>

<script>
import TodoList from '../components/todo/TodoList.vue'

// check_status: [todo, done, canceled]

export default {
  name: 'Home',
  components: {
    TodoList,
  },
  data() {
    return {
      todoLists: [
        {
          list_name: 'Today',
          todos: [{
              id: 1,
              content: 'First thing',
              check_status: 'todo'
            },
            {
              id: 2,
              content: 'Second todo',
              check_status: 'done'
            },
            {
              id: 3,
              content: 'Third todo',
              check_status: 'canceled'
            },
          ]
        },
        {
          list_name: 'Soon',
          todos: [{
              id: 4,
              content: 'First thing',
              check_status: 'todo'
            },
            {
              id: 5,
              content: 'Second todo',
              check_status: 'todo'
            },
            {
              id: 6,
              content: 'Third todo',
              check_status: 'todo'
            },
          ]
        }
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

.relative-sidebar {
  position: relative;
  left: 30px;
}
</style>

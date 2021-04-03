<template>
<div id="app">
  <Sidebar />
  <TodoList v-for="list in todoLists" :key="list.list_name" :todoList="list" />
</div>
</template>

<script>
import Sidebar from '../components/todo/Sidebar.vue'
import TodoList from '../components/todo/TodoList.vue'

// check_status: [todo, done, canceled]

export default {
  name: 'Home',
  components: {
    TodoList,
    Sidebar,
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
* {
  background-color: #252824;
}
</style>

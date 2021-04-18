<template>
  <div class="todo">
    <h1>{{ todoList.list_name }}</h1>
    <ul>
      <input v-model="newTodo" @keyup.enter='addNewTodo'>
      <br><br>
      <li v-for="todo in todoList.todos" :key="todo.content">
        <Todo draggable="true" :todo="todo" @delete="deleteTodo"/>
      </li>
    </ul>
  </div>
</template>

<script>
import Todo from './Todo.vue'

export default {
  name: 'TodoList',
  components: {
    Todo
  },
  props: {
    todoList: Object
  },
  data() {
    return {
      newTodo: ""
    }
  },
  methods: {
    addNewTodo: function() {
      // avoid create empty todo
      if(this.newTodo.length <= 1) {
        return;
      }
      this.todoList.todos.push({ content: this.newTodo, check_status: 'todo' });
      this.newTodo = "";
    },
    deleteTodo: function(todo) {
      // todos: [{id: 5}, {id: 3}, ...]
      var index = this.todoList.todos.indexOf(todo);
      if(index == -1) {
        return
      }
      this.todoList.todos.splice(index, 1);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
div {
  text-align: left;
}
ul {
    list-style-type:none;
}
</style>

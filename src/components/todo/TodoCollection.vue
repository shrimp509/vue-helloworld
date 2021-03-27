<template>
  <div class="todo">
    <h1>TODO Practice</h1>
    <ul>
      <li>
        <TodoList id="today_list" :things="things"/>
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
    things: Array
  },
  data() {
    return {
      newTodo: ""
    }
  },
  methods: {
    addNewTodo: function() {
      if(this.newTodo.length <= 1) {
        return;
      }
      this.things.push({ content: this.newTodo, checked: false });
      this.newTodo = "";
    },
    updateThings: function(thing) {
      var index = this.things.indexOf(thing);
      this.things.splice(index, 1);
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

<template>
  <div class="todo">
    <h1>TODO Practice</h1>
    <ul>
      <input v-model="newTodo" @keyup.enter='addNewTodo'>
      <br><br>
      <li v-for="thing in things" :key="thing.id">
        <Todo :thing="thing" @update="updateThings"/>
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
      this.things.push(this.newTodo);
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

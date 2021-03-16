<template>
  <div class="todo">
    <ul>
      <li v-for="thing in things" :key="thing.id">
        <Todo :thing="thing" />
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
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
ul {
    list-style-type:none;
}
</style>

<template>
  <div class="todo">
    <li>
      <label class="checked">
        <input type="checkbox" v-model="todo.check_status">{{ todo.content }}
      </label>
      <button class="btn btn-danger" @click="deleteTodo">Delete</button>
    </li>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
    todo: Object
  },
  data() {
    return {
    }
  },
  methods: {
    deleteTodo: function() {
      this.$emit('delete', this.todo);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
button {
  margin-left: 10px;
  font-size: 10px;
  padding: 3px;
}

input {
  margin-right: 5px;
}

.checked {
  text-decoration: line-through;
}
</style>

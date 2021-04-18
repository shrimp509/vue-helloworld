<template>
  <div class="todo">
    <li>
      <label>
        <input type="checkbox" v-model="checkStatus"><p :class="todoClass">{{ todo.content }}</p>
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
  },
  computed: {
    checkStatus: {
      cache: false,
      set: function(new_status) {
        this.todo.check_status = new_status == true ? 'done' : 'todo';
      },
      get: function() {
        var status = this.todo.check_status;
        return status == 'done' || status == 'canceled' ? true : false;
      }
    },
    todoClass: function() {
      return this.todo.check_status == 'done' ? 'done' : 'undone';
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

p {
  display: inline;
}

.done {
  text-decoration: line-through;
}

.undone {
  text-decoration: none;
}
</style>

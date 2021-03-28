<template>
  <div class="todo">
    <li>
      <label>
        <input type="checkbox" v-model="checkStatus">{{ todo.content }}
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
        console.log(this.todo);
      },
      get: function() {
        var status = this.todo.check_status;
        return status == 'done' || status == 'canceled' ? true : false;
      }
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

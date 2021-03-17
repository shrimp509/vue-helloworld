<template>
  <div class="todo">
    <li>
      <label>
        <input type="checkbox">{{ thing }}
      </label>
      <button class="btn btn-danger" @click="deleteTodo">Delete</button>
    </li>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
    thing: String
  },
  methods: {
    deleteTodo: function() {
      this.$emit('update', this.thing);
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
</style>

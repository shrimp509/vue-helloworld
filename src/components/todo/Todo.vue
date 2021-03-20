<template>
  <div class="todo">
    <li>
      <label class="checked">
        <input type="checkbox" v-model="thing.checked">{{ thing.content }}
      </label>
      <button class="btn btn-danger" @click="deleteTodo">Delete</button>
    </li>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
    thing: Object
  },
  data() {
    return {
      checkStyle: "line-through"
    }
  },
  methods: {
    deleteTodo: function() {
      this.$emit('update', this.thing.content);
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

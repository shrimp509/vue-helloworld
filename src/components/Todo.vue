<template>
  <div class="todo">
    <li>
      <label>
        <input type="checkbox">{{ thing }}
      </label>
      <button>Delete</button>
    </li>
  </div>
</template>

<script>
export default {
  name: 'Todo',
  props: {
    thing: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

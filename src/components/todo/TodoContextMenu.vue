<template>
  <div class="menu">
    <ul id="menu-ul">
      <li><p class="cmd">Cancel</p><p class="shortcut">⌘C</p></li>
      <li><p class="cmd">Delete</p><p class="shortcut">⌘D</p></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TodoContextMenu',
  props: {
    todo: Object
  },
  data() {
    return {
    }
  },
  methods: {
  },
  computed: {
  }
}
</script>

<style>
* {
  margin: 0px;
  padding: 0px;
}

.menu {
  height: 60px;
  width: 150px;
  border-radius: 5px 5px 5px 5px;
  border: 1px solid #FFFFFF55;
  box-shadow: 3px 5px 10px 1px black;
}

#menu-ul {
  list-style-type: none;
  padding: 5px 10px 5px 10px;
}

.cmd {
  display: inline;
  color: #FFFFFF;
}

.shortcut {
  float: right;
  color: #7B7D7B;
  font-size: 10px;
}
</style>

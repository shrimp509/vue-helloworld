<template>
  <div class="sidebar">
    <ul>
      <li><img src="https://cdn.icon-icons.com/icons2/2119/PNG/512/google_icon_131222.png" width="30px"><a href="/">Home</a></li>
      <li><a href="/todo">Todo</a></li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  props: {
  },
  data() {
    return {

    }
  },
  methods: {

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

ul {
  list-style-type: none;
  margin: auto;
  margin-left: 30px;
  margin-right: 30px;
}

li {
  text-align: left;
  padding-bottom: 10px;
}

li img {
  padding-right: 10px;
}

.sidebar {
  height: 100%; /* Full-height: remove this if you want "auto" height */
  width: 10%; /* Set the width of the sidebar */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */
  z-index: 1; /* Stay on top */
  top: 0; /* Stay at the top */
  left: 0;
  background-color: #F5F6F8;
  overflow-x: hidden; /* Disable horizontal scroll */
  padding-top: 5%;
}
</style>

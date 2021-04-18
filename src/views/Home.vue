<template>
  <div class="home">
    <h2 id="title">RS's CSS Practice</h2>
    <hr id="title-divider">
    <div id="nav">
      <router-link class="nav-item" to="/">Home</router-link>
      <router-link class="nav-item" to="/todo">Todo</router-link>
    </div>
    <hr id="nav-divider">
    <img alt="Vue logo" src="../assets/logo.png">
    <HomePage />
  </div>
</template>

<script>
// @ is an alias to /src
import HomePage from '@/components/home/Home.vue'

export default {
  name: 'Home',
  components: {
    HomePage
  }
}
</script>

<style>

#title-divider {
  border-width: 4px;
  border-color: #123456;
  opacity: 80%;
  width: 80%;
  border-radius: 10px;
}

#nav-divider {
  border-width: 1px;
  border-color: #123456;
  opacity: 50%;
  width: 80%;
  border-radius: 10px;
}


#nav {
  padding: 10px;
  margin: 10px;
}

#nav a {
  font-weight: bold;
  color: #42b983;
}

#nav a.router-link-exact-active {
  color: #2c3e50;
}

#title {
  margin: 30px;
}

.nav-item {
  margin: 20px;
}
</style>

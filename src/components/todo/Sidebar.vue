<template>
  <div class="sidebar">
    <a href='/' id="home">Home</a>
    <hr>
    <ul id="inbox">
      <li draggable="true"><img src="@/assets/inbox.png" class="sidebar-icon"><a :href="currentRoutePath + '/inbox'">收件箱</a></li>
    </ul>
    <ul id="time-related">
      <li draggable="true"><img src="@/assets/today.png" class="sidebar-icon"><a :href="currentRoutePath + '/today'">今天</a></li>
      <li draggable="true"><img src="@/assets/coming.png" class="sidebar-icon"><a :href="currentRoutePath + '/coming'">即將到來</a></li>
      <li draggable="true"><img src="@/assets/anytime.png" class="sidebar-icon"><a :href="currentRoutePath + '/anytime'">任何時間</a></li>
      <li draggable="true"><img src="@/assets/someday.png" class="sidebar-icon"><a :href="currentRoutePath + '/someday'">將來某天</a></li>
    </ul>
    <ul id="archive">
      <li draggable="true"><img src="@/assets/record.png" class="sidebar-icon"><a :href="currentRoutePath + '/record'">記錄簿</a></li>
      <li draggable="true"><img src="@/assets/trash.png" class="sidebar-icon"><a :href="currentRoutePath + '/trash'">垃圾桶</a></li>
    </ul>
    <div id="footer">
      <hr id="footer-divider">
      <button id="add-list-btn">＋ 新清單</button>
      <img src="@/assets/setting.png" class="sidebar-icon" id="footer-setting">
    </div>
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

  },
  computed: {
    currentRoutePath() {
      return this.$route.path;
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

* {
  font-size: 14px;
  font-weight: bold;
  color: #D1D1CF;
}

ul {
  list-style-type: none;
  margin-bottom: 15px;
  background-color: inherit;
  padding: 0px 10px 0px 10px;
}

li {
  text-align: left;
  background-color: inherit;
  border-radius: 5px;
  padding: 5px;
}

.sidebar {
  height: 100%; /* Full-height: remove this if you want "auto" height */
  width: 12%; /* Set the width of the sidebar */
  position: fixed; /* Fixed Sidebar (stay in place on scroll) */
  z-index: 100; /* Stay on top */
  top: 0; /* Stay at the top */
  background-color: #1C1F1B;
  padding-top: 50px;
  border-radius: 0px 5px 5px 0px;
}

.sidebar-icon {
  width: 20px;
  margin-right: 10px;
}

li:hover {
  background-color: #393C39;
}

a:hover {
  color: #D1D1CF;
  text-decoration: none;
}

#home {
  font-size: 20px;
  font-weight: bolder;
  padding-bottom: 100px;
}

#footer-divider {
  margin: 8px;
  background-color: #121212;
}

#footer {
  position: absolute;
  left: 0px;
  right: 0px;
  bottom: 10px;
  background-color: inherit;
}

#add-list-btn {
  margin-left: 20px;
  float: left;
  border: 0px;
  background-color: inherit;
}

#add-list-btn:hover {
  border-radius: 5px;
  border: 1px solid #555555;
}

#footer-setting {
  float: right;
  width: 25px;
  padding: 3px;
  background-color: inherit;
}

#footer-setting:hover {
  border-radius: 5px;
  border: 1px solid #555555;
}
</style>

<template>
  <div class="todo">
    <li @contextmenu.prevent="todoContextMenu">
      <label>
        <input type="checkbox" v-model="checkStatus"><p :class="todoClass">{{ todo.content }}</p>
      </label>
      <button class="btn btn-danger" @click="deleteTodo">Delete</button>
    </li>
    <Menu :class="isShowMenu" :todo="todo" :position="this.position" />
  </div>
</template>

<script>
import Menu from './TodoContextMenu.vue'

export default {
  name: 'Todo',
  components: {
    Menu
  },
  props: {
    todo: Object
  },
  data() {
    return {
      showMenu: false,
      position: {}
    }
  },
  methods: {
    deleteTodo: function() {
      this.$emit('delete', this.todo);
    },
    todoContextMenu: function(event) {
      this.showMenu = !this.showMenu;
      this.position = {
        'x': event.x,
        'y': event.y
      }
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
    },
    isShowMenu: function() {
      return this.showMenu == true ? 'show-menu' : 'hide-menu';
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

.show-menu {
  display: block;
}

.hide-menu {
  display: none;
}
</style>

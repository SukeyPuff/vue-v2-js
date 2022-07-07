<template>
  <div>
      {{ username }}
      <todo-item label="Username" v-bind:title.sync="username"></todo-item>
  </div>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  name: 'HelloWorld',
  components: {
    TodoItem
  },
  data() {
    return {
      username: 'Tom'
    }
  }
}
</script>

<style scoped>
</style>

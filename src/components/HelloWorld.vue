<template>
  <div>
      <todo-item v-model="lovingVue"></todo-item>
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
      lovingVue: true
    }
  }
}
</script>

<style scoped>
</style>

<template>
  <ol>
    <todo-item
      v-for="item in groceryList" 
      v-bind:todo="item"
      v-bind:key="item.id"
    ></todo-item>
  </ol>
</template>

<script>
import TodoItem from './TodoItem.vue'

export default {
  name: 'HelloWorld',
  data() {
    return {
      groceryList: [
      { id: 0, text: '蔬菜' },
      { id: 1, text: '奶酪' },
      { id: 2, text: '随便' }
    ]
    }
  },
  components: {
    TodoItem
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

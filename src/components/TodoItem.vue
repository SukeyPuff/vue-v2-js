<template>
  <div>
    <label>{{ label }}: </label>
    <input
      :value="title"
      @input="$emit('update:title', $event.target.value)"
    >
  </div>
</template>

<script>
export default {
  name: 'TodoItem',
  props: {
    label: String,
    title: String
  }
}
</script>

<style>

</style>
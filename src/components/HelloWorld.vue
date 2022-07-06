<template>
  <div>
    <p>{{message}}</p>
    <p>{{reverseMessage}}</p>
  </div>
</template>

<script>

export default {
  name: 'HelloWorld',
  data() {
    return {
      message: 'Hello'
    }
  },
  computed: {
    reverseMessage: function() {
      return this.message.split('').reverse().join('')
    }
  } 
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>

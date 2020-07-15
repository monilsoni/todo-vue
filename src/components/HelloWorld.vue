<template>
  <div class="hello">
    <h3>{{ msg }}</h3>

  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 40px;
  padding: 10px;
  background: lightgreen;
  border-radius: 10px;
}
</style>

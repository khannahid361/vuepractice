<template>
  <div>
    <h1>ep 5</h1>
    <h2>{{ greet }}, {{ name }}! </h2>
    <h2 v-text="channel"></h2>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      'name' : 'Kamrul',
      'greet': 'Hello',
      'channel': 'CodeEvolution'
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

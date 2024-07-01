<template>
  <div>
    <h1>ep 5</h1>
    <h2>{{ greet }}, {{ name }}! </h2>
    <p v-html="channel"></p>
    <p v-html="channel2"></p>
    <h2 v-html="channel"></h2>
    <div v-html="hack"></div>
  </div>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      'name' : 'Kamrul',
      'greet': 'Hello',
      'channel': '<b>CodeEvolution</b>',
      'channel2': 'CodeEvolution',
      'hack' : `<a href="#" onclick="alert('You have been hacked')">Win A Prize</a>`
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

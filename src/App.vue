<template>
  <div>
    <h1>ep 7</h1>
    <h2>{{ greet }}, {{ name }}! </h2>
    <p v-html="channel"></p>
    <p v-html="channel2"></p>
    <h2 v-html="channel"></h2>
    <div v-html="hack"></div>
    <h2 :id="headingId">Binded id</h2>
    <button :disabled="isDisabled">Disabled</button>
    <button :disabled="isActive">Active and Pressable</button>
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
      'hack' : `<a href="#" onclick="alert('You have been hacked')">Win A Prize</a>`,
      'headingId': 'heading',
      'isDisabled' : true,
      'isActive' : false
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

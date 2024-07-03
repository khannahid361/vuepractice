<template>
  <div>
    <h1>ep 9</h1>
    <h2>{{ greet }}, {{ name }}! </h2>
    <p v-html="channel"></p>
    <p v-html="channel2"></p>
    <h2 v-html="channel"></h2>
    <div v-html="hack"></div>
    <h2 :id="headingId">Binded id</h2>
    <button :disabled="isDisabled">Disabled</button>
    <button :disabled="isActive">Active and Pressable</button>
    <p :class="show1class && myclass">class is active</p>
    <p :class="show1class && secondclass">class is disabled</p>
    <p :class="[pomt,myclass]">Double class</p>
    <p :class="[show1class ? secondclass : myclass, pomt ]">Conditional class</p>
    <p :class="{
      'text-red': isDisabled,
      'text-green': show2class
    }">Object Conditional class - note the left side class has to be the css class</p>

    <h2 :style="{
      color: highlught,
      fontSize : sizeoffont + 'px'
    }">Working on inline style binding from data property</h2>

    <h2 :style="styleObject">Using Styling Object</h2>
    <h2 :style="[styleObject, specialFont]">Using Multiple Styling Object</h2>

    <h1>Conditional Binding V-if, else, elseif and V-show episode 11</h1>
    <h4 v-if="num===0">The Number is Zero</h4>
    <h4 v-else-if="num > 0">The Number is Positive</h4>
    <h4 v-else-if="num < 0">The Number is Negative</h4>
    <h4 v-else>Not A Number</h4>
    <template v-if="isDisplay">
      <h4>lol</h4>
      <h4>lo2X</h4>
      <h4>lo553</h4>
    </template>
  </div>
</template>

<script>

  export default {
    name: 'App',
    data() {
      return {
        'name': 'Kamrul',
        'greet': 'Hello',
        'channel': '<b>CodeEvolution</b>',
        'channel2': 'CodeEvolution',
        'hack': `<a href="#" onclick="alert('You have been hacked')">Win A Prize</a>`,
        'headingId': 'heading',
        'isDisabled': true,
        'isActive': false,
        'myclass': 'text-red',
        'secondclass': 'text-green',
        'show1class': true,
        'show2class': false,
        'pomt': 'promoted',
        'highlught': 'orange',
        'sizeoffont': 50,
        'styleObject': {
          color: 'orange',
          fontSize: '50px'
        },
        'specialFont': {
          fontStyle: 'italic'
        },
        'num': 'l',
        'isDisplay' : true,
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

  .text-red {
    color: red;
  }

  .text-green {
    color: rgb(29, 6, 235);
  }

  .promoted {
    font-style: italic;
  }
</style>
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
    <h1>episode 12 Vshow is used for toggling html</h1>
    <h4 v-show="showelements">pq</h4>
    <hr style="border: 1px solid black;">
    <h1>Episode 13 learning for loop</h1>
    <h4 v-for="(list, index) in lists" :key="index">{{ list }}-{{ index }}</h4>
    <h4 v-for="(dick, index) in fullnames" :key="index">{{ dick.first }} - {{ dick.last }}</h4>
    <div v-for="(actor, index) in actors" :key="index">
      <h3>{{ actor.identity }}</h3>
      <h5 v-for="like in actor.likes" :key="like">{{ like }}</h5>
    </div>
    <p v-for="(item, key, index) in balls" :key="index">{{ key }} - {{ item }} - {{ index }}</p>
    <hr style="border: 2px solid black;">
    <h1>Episode 15 Conditional List rendering</h1>
    <template v-for="friend in friends" :key="friend">
      <h3 v-if="friend === 'alif'">{{ friend }}</h3>
    </template>
    <hr style="border: 2px solid black;">
    <h1>Episode 16 Event Handling</h1>
    <h5>The Value Of 10, 20, 30 Addition is {{ add(10,20,30) }}</h5>
    <h5>The Value Of 5 X 10 = {{ multiplyBy10(5) }}</h5>
    <hr style="border: 2px solid black;">
    <h1>Episode 17 Event Handling</h1>
    <h2>{{ wife }}</h2>
    <button @click="wife = 'Naima'">Change Your wife</button>
    <h2>{{ count }}</h2>
    <button @click="increment(1)">Increment - 1</button>
    <button @click="increment(5)">Increment - 5</button>
    <button @click="decrement(1)">Decrement - 1</button>
    <button @click="decrement(5)">Decrement - 5</button>
    <hr style="border: 2px solid black;">
    <h1>Episode 19 Form Handling part 1</h1>
    <h2>{{ JSON.stringify(formValues, null, 2) }}</h2>
    <form>
      <div>
        <label for="myName">Name</label>
        <input type="text" name="myName" id="myName" v-model="formValues.myName">
      </div>
      <div>
        <label for="profile">Profile Summary</label>
        <textarea name="profile" id="profile" v-model="formValues.profileSummary"></textarea>
      </div>
      <div>
        <label for="country">Country</label>
        <select name="country" id="country" v-model="formValues.country">
          <option value="">Please Select</option>
          <option value="India">India</option>
          <option value="Pakistan">Pakistan</option>
          <option value="Bangladesh">Bangladesh</option>
        </select>
      </div>
      <div>
        <label for="job_location">Job Location</label>
        <select name="job_location" id="job_location" multiple v-model="formValues.jobLocation">
          <option value="India">India</option>
          <option value="Pakistan">Pakistan</option>
          <option value="Bangladesh">Bangladesh</option>
        </select>
      </div>
    </form>
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
        'isDisplay': true,
        'showelements': true,
        'lists': ['text', 'icon', 'font', 'lol'],
        'fullnames': [
          { first: 'a', last: 'b' },
          { first: 'c', last: 'd' },
          { first: 'e', last: 'f' },
          { first: 'g', last: 'h' },
          { first: 'i', last: 'j' }
        ],
        'actors': [
          { identity: 'A', likes: ['a', 'b'] },
          { identity: 'B', likes: ['c', 'd'] },
          { identity: 'C', likes: ['e', 'f'] },
          { identity: 'D', likes: ['g', 'h'] },
          { identity: 'E', likes: ['i', 'j'] }
        ],
        'balls': {
          name: 'tennis',
          color: 'green',
          bat: 'racket'
        },
        'friends': ['asad', 'hamza', 'alif'],
        'baseMultiplyer': 10,
        'wife': 'Nahida',
        'count': 0,
        formValues: {
          myName: '',
          profileSummary: '',
          country : '',
          jobLocation : []
        }
      }
    },
    methods: {
      add(a, b, c) {
        return a + b + c;
      },
      multiplyBy10(num) {
        return num * this.baseMultiplyer;
      },
      increment(x) {
        this.count += x;
      },
      decrement(y) {
        this.count -= y;
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
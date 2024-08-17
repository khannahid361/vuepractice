<template>
  <div>
    <h2>{{ name }}</h2>
    <button @click="changeName">Change Name</button>
    <h1 class="text-red">Changing Methods using refs</h1>
    <h2>{{ count }}</h2>
    <button @click="countValue">Increment</button>
    <h1 class="text-red">Changing Methods using reactive and to refs</h1>
    <h2>{{ first }} {{ last }}</h2>
    <button @click="changeHero">Change Hero</button>
  </div>
</template>

<script>
import { ref , reactive, toRefs } from 'vue';

export default {
  name: "ChangeMethod",
  setup() {
    const count = ref(0);
    const state = reactive({
        first : 'Habib',
        last : 'Al-Hakim'
    })
    function countValue() {
      count.value++;
      console.log(count.value);
    }
    function changeHero() { 
        state.first = 'Guddu';
        state.last = 'Vaiya';
     }
    return {
      count,
      countValue,
      ...toRefs(state),
      changeHero
    };
  },
  data() {
    return {
      name: "Ahmad Bin Rayhan",
    };
  },
  methods: {
    changeName() {
      this.name = "Ahmad Bin Rayhan Updated";
    },
  },
};
</script>

<style>
</style>
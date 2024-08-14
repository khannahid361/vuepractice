<template>
  <div>
    <h1>This is Click Counter Component</h1>
    <button @click="counterInc">Clicked {{ counter }}</button>
  </div>
</template>

<script>
import CounterMixin from "../mixins/counter";
export default {
  name: "ClickCounter",
  mixins: [CounterMixin]
};
</script>

<style>
</style>
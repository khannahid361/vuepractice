<template>
  <div>
    <h1 class="text-red">Props Component</h1>
    <h2>Hello {{ fullName }}</h2>
  </div>
</template>

<script>
import { computed } from "vue";
export default {
  name: "PersonGreeting",
  props: ["firstName", "lastName"],
  //   computed : {
  //     fullName() {
  //       return `${this.firstName} ${this.lastName}`;
  //     }
  setup(props) {
    const fullName = computed(() => {
      return `${props.firstName} ${props.lastName}`;
    });

    return{
        fullName,
    }
  },
};
</script>

<style scoped>
</style>
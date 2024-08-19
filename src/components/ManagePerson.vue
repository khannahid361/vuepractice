<template>
  <div>
    <input type="text" name="" id="" v-model="fname" />
    <input type="text" name="" id="" v-model="lname" />
  </div>
  <PersonGreeting :firstName="fname" :lastName="lname" />
</template>

<script>
import { ref } from "vue";
import PersonGreeting from "./PersonGreeting.vue";

export default {
  name: "ManagePerson",
  components: {
    PersonGreeting,
  },
  setup() {
    const fname = ref("");
    const lname = ref("");

    return {
      fname,
      lname,
    }
  }
};
</script>

<style scoped>
</style>
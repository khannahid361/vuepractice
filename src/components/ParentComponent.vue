<template>
  <div>
    <h1 style="color: green;">This is the Parent Component</h1>
    <child-component />
  </div>
</template>

<script>
import ChildComponent from "./ChildComponent.vue";
export default {
  components: { ChildComponent },
  name: "ParentComponent",
  component: {
    ChildComponent,
  },
};
</script>

<style scoped>
</style>
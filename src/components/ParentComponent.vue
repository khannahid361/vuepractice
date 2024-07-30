<template>
  <div>
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
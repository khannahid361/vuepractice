<template>
  <div>
    <h2>This is a Custom Event Component Pop Up</h2>
    <input type="text" v-model="aName" />
    <button @click="$emit('close', aName)">Close Pop Up</button>
    <h2 style="color: red">
      For closing any Pop up from child component we use $emit function in the
      template and emits array in export default. And we have to bind the event
      in App component as a custom event.
    </h2>
    <h1>Just See The emit object</h1>
  </div>
</template>

<script>
export default {
  name: "CustomEvent",
  emits: {
    close: (name) => {
        if(!name){
            return false
        }
        else{
            return true
        }
    }
  },
  data() {
    return {
      aName: "",
    };
  },
};
</script>

<style scoped>
</style>
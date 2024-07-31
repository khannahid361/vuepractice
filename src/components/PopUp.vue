<template>
    <div>
        <h2>This is a Pop Up</h2>
        <button @click="$emit('close','KingPin')">Close Pop Up</button>
        <h2 style="color: red;">For closing any Pop up from child component we use $emit function in the template and emits array in export default. And we have to bind the event in App component as a custom event</h2>
    </div>
</template>

<script>
    export default {
        name : 'PopUp',
        emits: ['close']
    }
</script>

<style scoped>

</style>
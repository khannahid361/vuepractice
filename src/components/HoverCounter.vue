<template>
    <div>
        <h1>This is Click Counter Component</h1>
        <h2 @mouseover="counterInc">Hovered {{ counter }}</h2>
    </div>
</template>

<script>
    import CounterMixin from "../mixins/counter"
    export default {
      name : 'HoverCounter',  
      mixins: [CounterMixin]
    }
</script>

<style>

</style>
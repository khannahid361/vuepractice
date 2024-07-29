<template>
    <div>
        <h1>I have Used The same Props but i made it dynamic by using vbind</h1>
        <h2 style="color:red">I am using Prop Property for FoodName = {{ foodName }} and Hero = {{ heroName }}</h2>
        <h1>Episode 30 done on Props</h1>
    </div>
</template>

<script>
    export default {
        name: 'SmartTool',
        props : ['foodName', 'heroName']
    }
</script>

<style scoped>

</style>

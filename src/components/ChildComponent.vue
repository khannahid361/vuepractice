<template>
    <div>
        <h1 style="color: red;">This is the Child Component</h1>
        <h2 style="color: blue;">I can get a value from App component to multi layer component without using Props. I did not had to pass to Master->Parent->Child passing the value using props. I simply had to Pass the value using Provide object and inject array</h2>
        <h1 style="color: red;">Here the My User Name Would be {{ myUserName }}</h1>
    </div>
</template>

<script>
    export default {
        name: 'ChildComponent',
        inject: ['myUserName']
    }
</script>

<style>

</style>
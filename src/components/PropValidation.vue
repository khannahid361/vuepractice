<template>
    <div>
        <h1>Here I added 2 props title = string and numericalValue = Number</h1>
        <h3 style="color: red;">The Title Is {{ title }}</h3>
        <h3 style="color: green;">The NumericalValue Is {{ numericalValue }}</h3>
        <h1 style="color: blue;">Please see the PropValidation Component to know how to use default , type, required property of an prop value</h1>
    </div>
</template>

<script>
    export default {
        name: 'PropValidation',
        props: {
            title: {
                type : String,
                required: true,
                default: 'Default Title',
            },
            numericalValue : Number,
        },
    }
</script>

<style>

</style>
<template>
    <div>
        <h2 style="color: red;" v-bind="$attrs">Hello i have added id property in this component without using props</h2>
        <h2 style="color: green;">If you want to see something different just comment or remove inheritAttrs: false which will make tha div and the h2 tag inside that div with that same id</h2>
    </div>
</template>

<script>
    export default {
        name: 'NonPropProperty',
        inheritAttrs: false,
    }
</script>

<style>

</style>
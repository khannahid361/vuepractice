<template>
    <div>
        <h1 style="color: red;">We will learn how to pass data to root componnt from child component using emit function and (input field)</h1>
        <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)">
        <h3 style="color: green;">@input="$emit('update:modelValue', $event.target.value)": This listens for the input event on the text field. When the event is triggered (i.e., when the user types in the input field), it emits an update:modelValue event with the new value of the input field ($event.target.value). The $emit method is used to emit a custom event.

            This setup is often used in custom Vue components to manually implement two-way data binding. It ensures that when the input value changes, the new value is sent back to the parent component, keeping the modelValue in sync.</h3>
    </div>
</template>

<script>
    export default {
        name: 'ComponentVmodel',
        props: {
            modelValue: String,
        }
    }
</script>

<style scoped>

</style>
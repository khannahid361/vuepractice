<template>
    <div>
        <h2>Template Ref Component</h2>
        <br>
        <input type="text" name="" ref="inputRef">
        <h2 class="red">I used ref in the Input field. then i focused on the input using the ref, like this.$refs.inputRef.focus() in the mounted method</h2>
    </div>
</template>

<script>
    export default {
        name: 'TemplateRef',
        mounted() {
            this.$refs.inputRef.focus();
        },
    }
</script>

<style>
.red{
    color: red;
}
</style>
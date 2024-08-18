<template>
    <div>
        <input type="text" name="" ref="inputRef">
        <h2 class="red">I used ref in the Input field. then i focused on the input using the ref, like this.$refs.inputRef.focus() in the mounted method</h2>
    </div>
</template>

<script>
    import { ref, onMounted} from 'vue'

    export default {
        name: 'ReplaceTemplateRef',
        setup() {
            const inputRef = ref(null)
            onMounted(() => {
             inputRef.value.focus()
            })
            return {
                inputRef
            }
        }
    }
</script>

<style>
.red{
    color: red;
}
</style>
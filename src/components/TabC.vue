<template>
    <div>
        Tab C Component
        <input type="text" v-model="keybord">
    </div>
</template>

<script>
    export default {
        name: 'TabC',
        data() {
            return {
                keybord: '',
            }
        },
    }
</script>

<style scoped>

</style>
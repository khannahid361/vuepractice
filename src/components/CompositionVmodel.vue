<template>
    <div>
        <input type="text" name="" id="" v-model="firstName">
        <input type="text" name="" id="" v-model="lastName">
        <h2>Composition Api</h2>
        <input type="text" name="" id="" v-model="heroName">
        <input type="text" name="" id="" v-model="first">
        <input type="text" name="" id="" v-model="last">
    </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue';
    export default {
        name: 'CompositionVmodel',
        setup() {
            const heroName = ref('')
            const state = reactive({
                first : '',
                last: ''
            })
            return{
                ...toRefs(state),
                heroName,
            }
        },
        data() {
            return {
                firstName : '',
                lastName : ''
            }
        },
    }
</script>

<style scoped>

</style>
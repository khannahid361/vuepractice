<template>
    <div>
        <input type="text" name="" id="" v-model="fname">
        <input type="text" name="" id="" v-model="lname">
        <h2>{{ fullName }}</h2>
        <h1 class="text-red">Computed replaced with ref</h1>
        <input type="text" name="" id="" v-model="refFname">
        <input type="text" name="" id="" v-model="refLname">
        <h2>Ref Fullname = {{ refFullname }}</h2>
        <h1 class="text-red">Computed replaced with Reactivity</h1>
        <input type="text" name="" id="" v-model="rcFirstname">
        <input type="text" name="" id="" v-model="rcLastname">
        <h2>Reactivve Fullname = {{ rcFullname }}</h2>
    </div>
</template>

<script>
import { ref, computed, reactive, toRefs } from 'vue';

    export default {
        name : 'ChangeComputed',
        setup() {
            const refFname = ref('')
            const refLname = ref('')
            const refFullname = computed(function(){
                return `${refFname.value} ${refLname.value}`
            })

            const state = reactive({
                rcFirstname : '',
                rcLastname : ''
            })
            const rcFullname = computed(function(){
                return `${state.rcFirstname} ${state.rcLastname}`
            })
            return {
                refFname,
                refLname,
                refFullname,
                ...toRefs(state),
                rcFullname
            }
        },
        data() {
            return {
                fname : '',
                lname : ''
            }
        },
        computed : {
            fullName () {
                return `Fullname = ${this.fname} ${this.lname}`
            }
        }
    }
</script>

<style scoped>

</style>
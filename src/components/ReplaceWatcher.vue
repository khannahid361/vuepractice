<template>
  <div>
    <input type="text" v-model="name" name="" id="" />
    <br>
    <br>
    <h1 class="text-red">Replacing Watcher to Composition Api Watcher</h1>
    <br>
    <br>
    <input type="text" v-model="firstName" name="" id="" />
    <br>
    <br>
    <input type="text" v-model="lastName" name="" id="" />
    <br>
    <br>
    <h1 class="text-red">Replacing Watcher to Composition Api Watcher</h1>
    <br>
    <br>
    <input type="text" v-model="fname" name="" id="" />
    <br>
    <br>
    <input type="text" v-model="lname" name="" id="" />
  </div>
</template>

<script>
import { ref, watch, reactive, toRefs } from 'vue';

    export default {
        name : 'ReaplaceWatcher',
        setup() {
            const firstName = ref('')
            const lastName = ref('Warner')
            watch([firstName, lastName], (newValues, oldValues) => {
                console.log(`First Name New value : ${newValues[0]}`);
                console.log(`First Name Old value : ${oldValues[0]}`);
                console.log(`last Name New value : ${newValues[1]}`);
                console.log(`last Name Old value : ${oldValues[1]}`);
            }, {
                immediate: true
            })

            const state = reactive({
                fname : '',
                lname: ''
            })
            watch(() => {
                return {...state}
            }, (newValue, oldValue) => {
                console.log(`First Name New value : ${newValue.fname}`);
                console.log(`First Name old value : ${oldValue.fname}`);
                console.log(`Last Name New value : ${newValue.lname}`);
                console.log(`Last Name old value : ${oldValue.lname}`);
            })
            return {
                firstName,
                lastName,
                ...toRefs(state)
            }
        },
        data() {
            return {
                name : ''
            }
        },
        watch : {
            name(newValue, oldValue) {
                console.log(`New value : ${newValue}`);
                console.log(`Old value : ${oldValue}`);
            }
        }
    }
</script>

<style scoped>
</style>
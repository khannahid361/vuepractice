<template>
  <div>
    <input type="text" v-model="name" name="" id="" />
    <br>
    <br>
    <h1>Replacing Watcher to Composition Api Watcher</h1>
    <br>
    <br>
    <input type="text" v-model="firstName" name="" id="" />
    <br>
    <br>
    <input type="text" v-model="lastName" name="" id="" />
  </div>
</template>

<script>
import { ref, watch } from 'vue';

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
            return {
                firstName,
                lastName
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
<template>
    <div>
        <h2 class="text-red">Options API - {{ o_firstName }}</h2>
        <h2 class="text-red">Composition API - {{ c_firstName }}</h2>
        <h3>{{ greet }}</h3>
        <hr style="border: 2px solid black" />
        <h1>Ep 53 - Replacing data with reactive</h1>
        <h2 class="text-red">Composition API with reactive since ref code is very uneasy</h2>
        <h3>{{ greetHero2 }}</h3>
        <h3 class="text-red">The ref function is used for single value where reactive function is used for object type values</h3>
    </div>
</template>

<script>
    import { ref, reactive } from 'vue';
    export default {
        name : 'ChangeData',
        setup() {
            const c_firstName = ref('Hamza')
            const c_lastName = ref('Islam')
            const c_heroName = ref('Batman')
            const greet = `Welcome to ${c_firstName.value} ${c_lastName.value} aka ${c_heroName.value}`;
            const state = reactive({
                firstName: 'Kent',
                lastName: 'Cody',
                heroName: 'SuperMan'
            })
            const greetHero2 = `Welcome to ${state.firstName} ${state.lastName} aka ${state.heroName}`;
            return{
                c_firstName : c_firstName,
                greet : greet,
                greetHero2: greetHero2
            }
        },

        data() {
            return {
                o_firstName: 'Golu Da',
            }
        },
    }
</script>

<style scoped>

</style>
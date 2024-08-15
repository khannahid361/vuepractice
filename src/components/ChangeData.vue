<template>
    <div>
        <h2 class="text-red">Options API - {{ o_firstName }}</h2>
        <h2 class="text-red">Composition API - {{ c_firstName }}</h2>
        <h3>{{ greet }}</h3>
    </div>
</template>

<script>
    import { ref } from 'vue';
    export default {
        name : 'ChangeData',
        setup() {
            const c_firstName = ref('Hamza')
            console.log(c_firstName);
            const greet = `Welcome to ${c_firstName.value}`;
            return{
                c_firstName : c_firstName,
                greet : greet
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
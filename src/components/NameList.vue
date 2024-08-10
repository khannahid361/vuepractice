<template>
    <div>
        <h3 v-for="frend in frendsList" :key="frend.firstName">
            <slot :firstName="frend.firstName" :lastName="frend.lastName"></slot>
        </h3>
    </div>
</template>

<script>
    export default {
        name: 'NameList',
        data() {
            return {
                frendsList : [
                    {
                        firstName: 'Selim',
                        lastName: 'Hossain'
                    },
                    {
                        firstName: 'Hadi',
                        lastName: 'Uzzaman'
                    },
                    {
                        firstName: 'Hasibul',
                        lastName: 'Hossain'
                    },
                    {
                        firstName: 'Nuru',
                        lastName: 'Milon'
                    },
                ]
            }
        },
    }
</script>

<style>

</style>
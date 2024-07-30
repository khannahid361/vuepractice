<template>
    <div>
        <parent-component />
    </div>
</template>

<script>
import ParentComponent from './ParentComponent.vue';

    export default {
        name: 'MasterComponent',
        components:{
            ParentComponent
        },
    }
</script>

<style scoped>

</style>
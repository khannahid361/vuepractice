<template>
    <div>
        <h1 style="color: blue;">This is the Grandfather Component</h1>
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
<template>
    <div>
        <h2>Child Component C</h2>
        <h2>Inject Value From Replace Provide Inject - {{ userName }}</h2>
        <h2>Composition Api  Provide Inject - {{ com_userName }}</h2>
        <h2>Composition Api  Ref - {{ childCount }}</h2>
        <h2>Composition Api  Reactive - {{ fname }}</h2>
    </div>
</template>

<script>
import { inject, toRefs } from 'vue';

    export default {
        name : 'ChildC',
        setup() {
            const apiname = inject('com_userName', 'Default Value')
            const childCount = inject('com_count', 0)
            const childState = inject('com_state', {})
            return {
                com_userName : apiname,
                childCount,
                ...toRefs(childState)
            }
        },
        inject : ['userName']
    }
</script>

<style scoped>

</style>
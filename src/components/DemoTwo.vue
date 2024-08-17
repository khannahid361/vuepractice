vbase <template>
    <div>
        <h1 class="text-red">I used To refs function for reactivity and to show value without using object</h1>
        <h1>{{ firstName }}</h1>
        <h1>{{ lastName }}</h1>
    </div>
</template>

<script>
    import { reactive, toRefs } from 'vue';

    export default {
        name: "DemoTwo",
        setup() {
            const state = reactive({
                firstName: 'Kamrul',
                lastName: 'Hasan'
            })
            setTimeout(() => {
                state.firstName = "Monkey"
                state.lastName = "Dancing"
            }, 10000)
            return toRefs(state)
        },
    };
</script>

<style>
</style>
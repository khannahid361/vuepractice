vbase <template>
    <div>
        <h2>Parent Component {{ name }}</h2>
        <ChildA />
        <button @click="incrementCount">Increment</button>
        <button @click="updateFname">Update Name</button>
    </div>
</template>

<script>
import { provide , ref, toRefs, reactive } from 'vue';
import ChildA from './ChildA.vue';
    export default {
        name : 'ReplaceProvideInject',
        setup() {
            provide('com_userName', 'KingKong');

            const count = ref(0)
            function incrementCount() {
                count.value++
            }
            provide('com_count', count);

            const state = reactive({
                fname : 'lol da'
            })
            function updateFname() {
                state.fname = 'new name'
            }
            provide('com_state', state)

            return {
                count,
                ...toRefs(state),
                incrementCount,
                updateFname
            }
        },
        components : {
            ChildA
        },
        data() {
            return {
                name : 'Vue Practice'
            }
        },
        provide() {
            return {
                userName : this.name
            }
        }
    }
</script>

<style scoped>

</style>
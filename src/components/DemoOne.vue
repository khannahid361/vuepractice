vbase <template>
  <div>
    <h1>{{ name }}</h1>
  </div>
</template>

<script>
import { ref } from 'vue';

export default {
  name: "DemoOne",
  setup() {
    const name = ref("This is Demo One Component");
    setTimeout(() => {
        name.value = "This is Demo One Component (Updated)";
        console.log("Updated name:", name);
    }, 2000);
    return {
      name,
    };
  },
};
</script>

<style>
</style>
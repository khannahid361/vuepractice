<template>
    <div>
        <h4>Child Styles Component Text</h4>
        <p>To Ensure Child Style / App style do not over ride one another we use scoped style in child Component</p>
        <h2 style="color:red">If you use slot property the parent style will be embeded to the child component it is fixed</h2>
    </div>
</template>

<script>
    export default {
        name: 'ChildStyles'
    }
</script>

<style scoped>
h4 {
  color: olivedrab;
}
</style>
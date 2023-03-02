<template>
  <label>
    {{ label }}
    <input type="text"/>
  </label>
</template>

<script>
export default {
  name: "CustomInput",
  props: ['label']
}
</script>

<style scoped>

</style>
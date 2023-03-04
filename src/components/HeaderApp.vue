<template>
<header>
  <h1>{{title}}</h1>
  <ButtonHeader/>
</header>
</template>

<script>

import ButtonHeader from "@/components/ButtonHeader.vue";

export default {
  name: "HeaderApp",
  props:['title'],
  components: {ButtonHeader}
}
</script>

<style scoped>
header{
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>
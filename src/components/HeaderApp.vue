<template>
<header>
  <h1>{{title}}</h1>
  <button-header text="Add Tasks" color="green"/>
</header>
</template>

<script>

import ButtonHeader from "@/components/ButtonHeader.vue";

export default {
  name: "HeaderApp",
  props:{
    title:String,

  },
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
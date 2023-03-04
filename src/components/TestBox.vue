<template>
  <div class="box"> {{ boxName }} </div>
</template>

<script>
export default {
  props:['boxName'],
  name: "TestBox",
  data(){
    return{

    }
  },
  created() {
  console.log('created')
    },
  mounted() {
    console.log('mounted')
    },
  unmounted() {
    console.log('unmounted')
    },
}
</script>;;

<style scoped>
.box {
  background-color: darkorange;
  width: 100px;
  text-align: center;
  margin-top: 10px;
}
</style>
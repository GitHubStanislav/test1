<template>
<div v-for="task in tasksList" :key="task.id" >
  <task-item :task="task"/>
</div>

</template>

<script>
import TaskItem from "@/components/TaskItem.vue";
export default {
  name: "TasksGet",
  components:{TaskItem},
  props:{
    tasksList: Array
  }
}
</script>

<style scoped>

</style>
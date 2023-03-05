<template>
  <div v-for="task in tasksList" :key="task.id">
    <task-item @delete-task="$emit('delete-task', task.id)" :tasksList="task" />
  </div>
</template>

<script>
import TaskItem from '@/components/TaskItem.vue'
export default {
  name: 'TasksGet',
  components: { TaskItem },
  props: {
    tasksList: Array
  },
  emits:['delete-task',]
}
</script>

<style scoped></style>

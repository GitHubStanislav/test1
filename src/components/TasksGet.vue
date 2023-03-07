<template>
  <div v-for="task in tasksList" :key="task.id">
    <TaskItem
      @delete-task="$emit('delete-task', task.id)"
      @toggle-reminder="$emit('toggle-reminder', task.id)"
      :tasksList="task"
    />
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
  emits: ['delete-task', 'toggle-reminder']
}
</script>

<style scoped></style>

<template>
  <div @dblclick="$emit('toggle-reminder',tasksList.id)" :class="[tasksList.reminder? 'reminder' : '', 'task']">
    <h3>
      {{ tasksList.text }}
      <i @click="$emit('delete-task',tasksList.id)" class="fas fa-times"></i>
    </h3>
    <p>{{ tasksList.day }}</p>
  </div>
</template>

<script>
export default {
  name: 'TaskItem',
  props:['tasksList'],
}
</script>

<style scoped>
.fas{
  color:red;
}
.task {
  background: #f4f4f4;
  margin: 5px;
  padding: 10px 20px;
  cursor: pointer;
}

.task.reminder {
  border-left: 5px solid green;
}

.task h3 {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>

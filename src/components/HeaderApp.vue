<template>
  <header>
    <h1>{{ title }}</h1>
    <ButtonHeader
      @btn-click="$emit('toggle-add-task')"
      :text="showAddTask ? 'Close' : 'Add Task'"
      :color="showAddTask ? 'red' : 'green'"
    />
  </header>
</template>

<script>
import ButtonHeader from '@/components/ButtonHeader.vue'

export default {
  name: 'HeaderApp',
  props: {
    title: String,
    showAddTask: Boolean
  },
  components: { ButtonHeader }
}
</script>

<style scoped>
header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 20px;
}
</style>

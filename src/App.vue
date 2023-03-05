<template>
  <div class="container">
    <header-app :title="titleHeader" />
    <tasks-get @delete-task="deleteTask" :tasksList="tasks" />
  </div>
</template>

<script>
import HeaderApp from '@/components/HeaderApp.vue'
import TasksGet from '@/components/TasksGet.vue'

export default {
  components: {
    HeaderApp,
    TasksGet
  },
  data() {
    return {
      titleHeader: 'Hello',
      tasks: []
    }
  },
  created() {
    this.tasks = [
      {
        id: 1,
        text: 'Doctor Appointment',
        day: 'March 1st',
        reminder: true
      },
      {
        id: 2,
        text: 'Meeting at School',
        day: 'March 3rd',
        reminder: true
      },
      {
        id: 3,
        text: 'Food Shopping',
        day: 'March 3rd',
        reminder: false
      }
    ]
  },
  methods: {
    deleteTask(id){
this.tasks = this.tasks.filter((task)=> task.id !== id)
    console.log('task', id)
    }
  },
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

body {
  font-family: 'Poppins', sans-serif;
}

.container {
  max-width: 500px;
  margin: 30px auto;
  overflow: auto;
  min-height: 300px;
  border: 1px solid steelblue;
  padding: 30px;
  border-radius: 5px;
}

.btn {
  display: inline-block;
  background: #000;
  color: #fff;
  border: none;
  padding: 10px 20px;
  margin: 5px;
  border-radius: 5px;
  cursor: pointer;
  text-decoration: none;
  font-size: 15px;
  font-family: inherit;
}

.btn:focus {
  outline: none;
}

.btn:active {
  transform: scale(0.98);
}

.btn-block {
  display: block;
  width: 100%;
}
</style>

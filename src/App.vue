<template>
  <div class="container">
    <HeaderApp
        :title="titleHeader"
        @toggle-add-task="toggleAddTask"
        :showAddTask="showAddTask"
    />
    <div v-if="showAddTask">
      <AddTask @add-task="addTask"/>
    </div>
    <TasksGet
        @delete-task="deleteTask"
        @toggle-reminder="toggleReminder"
        :tasksList="tasks"/>
  </div>
</template>

<script>
import HeaderApp from '@/components/HeaderApp.vue'
import TasksGet from '@/components/TasksGet.vue'
import AddTask from "@/components/AddTask.vue";

export default {
  components: {
    HeaderApp,
    TasksGet,
    AddTask
  },
  data() {
    return {
      titleHeader: 'Hello',
      tasks: [],
      showAddTask: false
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
    toggleAddTask(){
      this.showAddTask = !this.showAddTask
    },
    addTask(task) {
      this.tasks = [...this.tasks, task]
    },

    deleteTask(id) {
      if (confirm('Are you sure ?')) {
        this.tasks = this.tasks.filter((task) => task.id !== id)
        console.log('task', id)
      }

    },
    toggleReminder(id) {
      this.tasks = this.tasks.map((task) => task.id === id ?
          {...task, reminder: !task.reminder} : task)
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

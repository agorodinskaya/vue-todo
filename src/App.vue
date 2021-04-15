<template>
<div class="container">
  <Header title="task tracker"/>
  <AddTask/>
  <Tasks @toggle-reminder="toggleReminder" @delete-task="deleteTask" :tasks='tasks'/>
  </div>
</template>

<script>
import Header from './components/Header'
import Tasks from './components/Tasks'
import AddTask from './components/AddTask'

export default {
  name: 'App',
  components: {
    Header,
    Tasks,
    AddTask
  },
  data() {
    return {
      tasks : []
    }
  },
  methods: {
    deleteTask(id) {
      if(confirm('Please confirm you want to delete')) {
        this.tasks = this.tasks.filter(task => task.id !== id)
      }
    },
    toggleReminder(id) {
      this.tasks = this.tasks.map(task => task.id === id ? {...task, reminder: !task.reminder } : task)
    }
  },
  created() {
    this.tasks = [
      {
         id: 1,
         text: 'code',
         day: '15 April 2021',
         reminder: true
    },
      {
         id: 2,
         text: 'drink coffee',
         day: '16 April 2021',
         reminder: true
    },
      {
         id: 3,
         text: 'walk',
         day: '16 April 2021',
         reminder: false
    },
    ]
  },

}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400&display=swap');
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
body {
  font-family: 'Poppins', sans-serif;
}
.container {
  max-width: 50vw;
  margin: 30px auto;
  overflow: auto;
  min-height: 50vh;
  border: 1px solid #b446af;
  padding: 30px;
  border-radius: 5px;
  box-shadow: 3px 3px #2503204d;
}
.btn {
  display: inline-block;
  background: #08022ce0;
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

.btn:hover {
  background: #840af7a1;
  color: #250320;
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

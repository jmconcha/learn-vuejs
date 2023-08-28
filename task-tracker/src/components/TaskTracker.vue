<script setup>
  import { ref } from 'vue';
  import TaskForm from '@/components/TaskForm.vue';
  import TaskList from '@/components/TaskList.vue';

  const showTaskForm = ref(false);
  const taskList = ref([
    {
      id: 0,
      text: 'cook breakfast',
      dayAndTime: 'May 7th at 7:00am',
      done: false,
      reminder: false,
    },
    {
      id: 1,
      text: 'cook breakfast',
      dayAndTime: 'May 7th at 7:00am',
      done: true,
      reminder: false,
    },
    {
      id: 2,
      text: 'cook breakfast',
      dayAndTime: 'May 7th at 7:00am',
      done: false,
      reminder: true,
    },
    {
      id: 3,
      text: 'cook breakfast',
      dayAndTime: 'May 7th at 7:00am',
      done: true,
      reminder: true,
    },
  ]);
  
  function addTask(task) {
    taskList.value.unshift({
      id: taskList.value.length,
      text: task.text,
      dayAndTime: task.dayAndTime,
      reminder: task.reminder,
      done: false,
    });
  }
  function toggleDone(id) {
    taskList.value.forEach(task => {
      if (task.id === id) {
        task.done = !task.done;
      }
    });
  }
  function removeTask(id) {
    taskList.value = taskList.value.filter(task => task.id !== id);
  }
  function reminder(id) {
    taskList.value.forEach(task => {
      if (task.id === id) {
        task.reminder = !task.reminder;
      }
    });
  }
</script>

<template>
  <div class="header">
    <h1>Task Tracker</h1>
    <button v-if="!showTaskForm" @click="showTaskForm = !showTaskForm" class="primary">Add Task</button>
    <button v-if="showTaskForm" @click="showTaskForm = !showTaskForm" class="danger">Close</button>
  </div>

  <div class="body">
    <TaskForm v-if="showTaskForm" @addTask="addTask" />
    <TaskList
      v-if="taskList.length > 0"
      :taskList="taskList"
      @toggleDone="toggleDone"
      @removeTask="removeTask"
      @reminder="reminder"
    />
  </div>
</template>

<style scoped>
  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
    padding: 40px 30px 0 30px;
  }

  .header button {
    font-weight: 700;
  }

  .body {
    padding-left: 30px;
    padding-right: 30px;
  }
</style>
<script setup>
  import { ref } from 'vue';
  import TaskForm from './components/TaskForm.vue';
  import TaskList from './components/TaskList.vue';

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

  const currentYear = new Date().getFullYear();
  
  function addTask(task) {
    taskList.value.unshift({
      id: taskList.value.length,
      text: task.text,
      dayAndTime: task.dayAndTime,
      reminder: task.reminder,
      done: false,
    });
  }
</script>

<template>
  <div class="container">
    <div class="header">
      <h1>Task Tracker</h1>
      <button v-if="!showTaskForm" @click="showTaskForm = !showTaskForm" class="primary">Add Task</button>
      <button v-if="showTaskForm" @click="showTaskForm = !showTaskForm" class="danger">Close</button>
    </div>

    <div class="body">
      <TaskForm v-if="showTaskForm" @addTask="(task) => addTask(task)" />
      <TaskList v-if="taskList.length > 0" :taskList="taskList" />
    </div>

    <div class="footer">
      <span>Copyright &#169; {{ currentYear }}</span>
      <a href="#about">About</a>
    </div>
  </div>
</template>

<style scoped>
  .container {
    max-width: 500px;
    width: 100%;
    border-radius: 5px;
    border: 2px solid #9E9FA5;
    background-color: #F1F0E8;
  }

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

  .footer {
    font-size: 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 40px;
    padding: 20px 30px;
    border-top: 2px solid #9E9FA5;
  }
</style>

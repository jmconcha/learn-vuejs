<script setup>
  import TaskForm from './components/TaskForm.vue';
  import TaskList from './components/TaskList.vue';
</script>

<template>
  <div class="container">
    <div class="header">
      <h1>Task Tracker</h1>
      <button class="primary">Add Task</button>
    </div>

    <div class="body">
      <TaskForm />
      <TaskList />
    </div>

    <div class="footer">
      <span>Copyright &#169; 2023</span>
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

<script setup>
  import TaskListItem from './TaskListItem.vue';

  const taskList = [
    {
      id: 0,
      text: 'cook breakfast',
      dateAndTime: 'May 7th at 7:00am',
      done: false,
      reminder: false,
    },
    {
      id: 1,
      text: 'cook breakfast',
      dateAndTime: 'May 7th at 7:00am',
      done: true,
      reminder: false,
    },
    {
      id: 2,
      text: 'cook breakfast',
      dateAndTime: 'May 7th at 7:00am',
      done: true,
      reminder: true,
    },
    {
      id: 3,
      text: 'cook breakfast',
      dateAndTime: 'May 7th at 7:00am',
      done: false,
      reminder: true,
    },
  ];
</script>

<template>
  <div class="task-list">
    <ul>
      <li v-for="task in taskList" :key="task.id">
        <TaskListItem :task="task" />
      </li>
    </ul>
  </div>
</template>

<style scoped>
  .task-list {
    border-right: 2px solid #9E9FA5;
    max-height: 300px;
    height: 100%;
    overflow-y: auto;
  }
  .task-list ul {
    list-style-type: none;
    padding: 0;
  }
</style>
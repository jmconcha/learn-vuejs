<script setup>
  import TaskListItem from './TaskListItem.vue';

  const props = defineProps({
    taskList: Array,
  })
</script>

<template>
  <div class="task-list">
    <ul>
      <li v-for="task in props.taskList" :key="task.id">
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
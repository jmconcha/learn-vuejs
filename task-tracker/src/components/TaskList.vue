<script setup>
  import TaskListItem from './TaskListItem.vue';

  const props = defineProps({
    taskList: Array,
  })

  const emit = defineEmits(['toggleDone', 'removeTask']);

  function onDoneToggle(id) {
    emit('toggleDone', id);
  }
  function onRemoveTask(id) {
    emit('removeTask', id);
  }
</script>

<template>
  <div class="task-list">
    <ul>
      <li v-for="task in props.taskList" :key="task.id">
        <TaskListItem :task="task" :onDoneToggle="onDoneToggle" :onRemoveTask="onRemoveTask" />
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
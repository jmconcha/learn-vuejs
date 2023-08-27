<script setup>
  import TrashIcon from './icons/TrashIcon.vue';
  import CheckIcon from './icons/CheckIcon.vue';

  const props = defineProps({
    task: {
      text: String,
      dayAndTime: String,
      done: Boolean,
      reminder: Boolean,
    },
  });
</script>

<template>
  <div
    :class="{
      'task-list-item': true,
      reminder: props.task.reminder,
      done: props.task.done,
    }">
    <div class="content">
      <h2>{{ props.task.text }}</h2>
      <p>{{ props.task.dayAndTime }}</p>
    </div>
    <div class="action">
      <button class="button-icon success">
        <CheckIcon />
      </button>
      <button class="button-icon error">
        <TrashIcon />
      </button>
    </div>
  </div>
</template>

<style scoped>
  .task-list-item {
    border: 2px solid #9E9FA5;
    margin-bottom: 16px;
    justify-content: space-between;
    align-items: center;
    padding: 8px 16px;
    cursor: pointer;
  }
  .task-list-item:hover {
    background-color: #e6e6e6;
  }
  .done {
    color: #218838;
    border-color: #1e7e34;
  }
  .reminder {
    border-left-color: #d39e00;
    border-left-width: 4px;
  }
  .action {
    display: flex;
    gap: 16px;
  }
  .button-icon {
    border: none;
    padding: 0;
  }
  .button-icon svg {
    fill: #9E9FA5;
    width: 20px;
    height: auto;
  }
</style>
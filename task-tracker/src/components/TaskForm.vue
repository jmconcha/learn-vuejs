<script setup>
  import { ref, onUnmounted } from 'vue';

  const emit = defineEmits(['addTask']);
  const text = ref('');
  const dayAndTime = ref('');
  const reminder = ref(false);

  onUnmounted(() => clearFormFields());

  function clearFormFields() {
    text.value = '';
    dayAndTime.value = '';
    reminder.value = false;
  }
  function onAddTask() {
    emit('addTask', {
      text: text.value,
      dayAndTime: dayAndTime.value,
      reminder: reminder.value,
    });

    clearFormFields();
  }
</script>

<template>
  <div class="form-container">
    <form @submit.prevent="onAddTask">
      <div class="form-group">
        <label for="task">Task</label>
        <input v-model="text" id="task" class="form-control" type="text" placeholder="Add Task">
      </div>
      <div class="form-group">
        <label for="dayAndTime">Day & Time</label>
        <input v-model="dayAndTime" id="dayAndTime" class="form-control" type="text" placeholder="Add Day & Time">
      </div>
      <div class="set-reminder">
        <input v-model="reminder" id="setReminder" type="checkbox">
        <label for="setReminder">Set Reminder</label>
      </div>
      <button type="submit" class="primary">Save Task</button>
    </form>
  </div>
</template>

<style scoped>
  .form-container {
    margin-bottom: 40px
  }

  .form-container .form-group{
    display: flex;
    flex-direction: column;
    margin-bottom: 20px;
  }
  .form-group label {
    font-size: 18px;
  }

  .form-group input {
    padding: 8px 14px;
    font-size: 16px;
    outline: none;
    border: 2px solid #9E9FA5;
  }

  .form-container .set-reminder {
    display: flex;
    align-items: center;
    margin-bottom: 20px;
    font-size: 18px;
  }
  .set-reminder input {
    margin-right: 10px;
    cursor: pointer;
    width: 20px;
    height: 20px;
  }
  .set-reminder label {
    user-select: none;
  }

  .form-container form > button {
    display: flex;
    align-items: center;
    justify-content: center;
    width: 100%;
    padding: 8px 14px;
    font-size: 18px;
    font-weight: 700;
  }
</style>
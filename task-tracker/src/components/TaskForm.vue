<template>
  <div class="form-container">
    <form action="#">
      <div class="form-group">
        <label for="task">Task</label>
        <input id="task" class="form-control" type="text" placeholder="Add Task">
      </div>
      <div class="form-group">
        <label for="dayAndTime">Day & Time</label>
        <input id="dayAndTime" class="form-control" type="text" placeholder="Add Day & Time">
      </div>
      <div class="set-reminder">
        <input id="setReminder" type="checkbox">
        <label for="setReminder">Set Reminder</label>
      </div>
      <button class="primary">Save Task</button>
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
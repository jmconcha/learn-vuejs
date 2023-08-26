<script setup>
  import TrashIcon from './components/icons/TrashIcon.vue';
</script>

<template>
  <div class="container">
    <div class="header">
      <h1>Task Tracker</h1>
      <button class="primary">Add Task</button>
    </div>

    <div class="body">
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

      <div class="task-list">
        <div class="task-list-item">
          <div class="content">
            <h2>Doctors Appointment</h2>
            <p>March 5th at 2:30pm</p>
          </div>
          <div class="action">
            <button class="button-icon">
              <TrashIcon />
            </button>
          </div>
        </div>
        <div class="task-list-item reminder">
          <div class="content">
            <h2>Meeting with boss</h2>
            <p>December 25 at 8:30am</p>
          </div>
          <div class="action">
            <button class="button-icon">
              <TrashIcon />
            </button>
          </div>
        </div>
        <div class="task-list-item done">
          <div class="content">
            <h2>Meeting with boss</h2>
            <p>December 25 at 8:30am</p>
          </div>
          <div class="action">
            <button class="button-icon">
              <TrashIcon />
            </button>
          </div>
        </div>
        <div class="task-list-item reminder done">
          <div class="content">
            <h2>Meeting with boss</h2>
            <p>December 25 at 8:30am</p>
          </div>
          <div class="action">
            <button class="button-icon">
              <TrashIcon />
            </button>
          </div>
        </div>
      </div>
    </div>

    <div class="footer">
      <span>Copyright &#169; 2023</span>
      <a href="#about">About</a>
    </div>
  </div>
</template>

<style scoped>
  button {
    padding: 0;
    color: #000;
    font-size: 16px;
    cursor: pointer;
    border-radius: 5px;
    padding: 8px 14px;
    outline: none;
  }
  .primary {
    color: #fff;
    background-color: #007bff;
    border: 1px solid #007bff;
  }
  .primary:hover {
    background-color: #0069D9;
  }

  .container {
    margin-top: 100px;
    max-width: 500px;
    width: 100%;
    padding: 40px 30px;
    border-radius: 5px;
    border: 2px solid #9E9FA5;
    background-color: #F1F0E8;
  }

  .header {
    display: flex;
    justify-content: space-between;
    align-items: center;
    margin-bottom: 20px;
  }

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

  .task-list .task-list-item {
    border: 2px solid #9E9FA5;
    margin-bottom: 16px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 8px 16px;
  }
  .task-list .done {
    color: #218838;
    border-color: #1e7e34;
  }
  .task-list .reminder {
    border-left-color: #d39e00;
    border-left-width: 4px;
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
  .button-icon svg:hover {
    fill: red;
  }
</style>

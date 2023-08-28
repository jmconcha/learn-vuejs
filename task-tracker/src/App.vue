<script setup>
  const currentYear = new Date().getFullYear();
</script>

<template>
  <div class="container">
    <router-view></router-view>

    <div class="footer">
      <span>Copyright &#169; {{ currentYear }}</span>
      <router-link to="/about">About</router-link>
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

  .footer {
    font-size: 16px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    margin-top: 40px;
    padding: 20px 30px;
    border-top: 1px solid #9E9FA5;
  }
</style>

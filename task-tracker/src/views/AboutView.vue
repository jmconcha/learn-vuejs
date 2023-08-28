<script setup>
  import router from '@/router';
</script>

<template>
  <div style="padding: 40px 30px 0;">
    <h1>Task Tracker</h1>
    <span style="margin-right: 8px;">Version 1.0.0</span>
    <a href="javascript:void(0)" @click="router.back()">Go Back</a>
  </div>
</template>
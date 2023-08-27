<script setup>
  import { ref, onMounted } from 'vue';

  const randomUser = ref(null);
  const loading = ref(false);

  onMounted(() => {
    fetchRandomUser();
  });

  async function fetchRandomUser() {
    loading.value = true;

    const res = await fetch('https://randomuser.me/api');
    const data = await res.json();
    console.log("🚀 ~ file: App.vue:16 ~ fetchRandomUser ~ data:", data.results[0])
    randomUser.value = data.results[0];

    loading.value = false;
  }
</script>

<template>
  <div v-if="randomUser !== null" class="container">
    <div :class="{ card: true, loading: loading }">
      <div class="content" v-if="!loading">
        <div class="imgContainer">
          <img :src="randomUser.picture.large" alt="profile picture" />
        </div>
        <span>{{ `${randomUser.name.title} ${randomUser.name.first} ${randomUser.name.last}`  }}</span>
        <span>{{ randomUser.dob.age }} years old</span>
        <span>I lived in {{ randomUser.location.street.name }}</span>
      </div>

      <h3 v-if="loading" class="loading">loading...</h3>

      <button @click="fetchRandomUser()" :disabled="loading">Get Random User</button>
    </div>
  </div>
</template>

<style scoped>
  .container {
    border: 1px solid red;
    width: 100vw;
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    font-family: Arial, Helvetica, sans-serif;
  }

  .card {
    width: 300px;
    min-height: 335px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    padding: 20px 20px 40px 20px;
    background-color: #e6e6e6;
    border-radius: 5px;
  }
  .loading {
    justify-content: flex-end;
  }

  .card .content {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  .card .imgContainer {
    margin-bottom: 20px;
    width: 128px;
    height: 128px;
    border-radius: 50%;
    border: 2px solid #808080;
    overflow: hidden;
  }

  img {
    width: 100%;
    height: auto;
    object-fit: cover;
  }

  .card button {
    margin-top: 16px;
    padding: 8px 14px;
    cursor: pointer;
    font-size: 16px;
    font-family: Arial, Helvetica, sans-serif;
  }
</style>

<template>
    <div class="profile-card">
      <div class="card-header" :class="{ 'card-header-active': isActive }" @click="toggleActive">
        <img :src="$auth.user.picture" class="profile-picture" />
      </div>
      <transition name="fade">
        <div v-if="isActive" class="card-body">
          <h2>{{ $auth.user.name }}</h2>
          <p>{{ $auth.user.email }}</p>
        </div>
      </transition>
      <div class="card-footer" :class="{ 'card-footer-active': isActive }">
        <pre>{{ JSON.stringify($auth.user, null, 2) }}</pre>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "ProfileCard",
    data() {
      return {
        isActive: false,
      };
    },
    methods: {
      toggleActive() {
        this.isActive = !this.isActive;
      },
    },
  };
  </script>
  
  <style>
  .profile-card {
    display: flex;
    flex-direction: column;
    align-items: center;
    background-color: #ffffff;
    border-radius: 10px;
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 400px;
    margin: 30px auto;
    overflow: hidden;
    transition: box-shadow 0.3s ease-in-out;
  }
  
  .card-header {
    background-color: #007bff;
    width: 100%;
    padding: 20px;
    display: flex;
    justify-content: center;
    cursor: pointer;
  }
  
  .card-header-active {
    box-shadow: 0 4px 12px rgba(0, 0, 0, 0.2);
  }
  
  .profile-picture {
    width: 100px;
    height: 100px;
    border-radius: 50%;
    border: 4px solid #ffffff;
    transition: transform 0.3s ease-in-out;
  }
  
  .card-body {
    padding: 20px;
    text-align: center;
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  
  h2,
  p {
    margin: 10px 0;
  }
  
  h2 {
    font-size: 22px;
    color: #333;
  }
  
  p {
    font-size: 16px;
    color: #666;
  }
  
  .card-footer {
    background-color: #f9f9f9;
    padding: 15px;
    font-family: "Courier New", Courier, monospace;
    font-size: 12px;
    color: #333;
    width: 100%;
  }
  
  .card-footer-active {
    display: flex;
    justify-content: center;
  }
  </style>
  
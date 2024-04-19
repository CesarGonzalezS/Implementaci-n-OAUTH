<template>
  <div id="app">
    <nav class="nav-links">
      <router-link to="/" class="nav-link">Home</router-link>|
      <router-link to="/about" class="nav-link">About</router-link>|
      <router-link v-if="$auth.isAuthenticated" to="/profile" class="nav-link">Profile</router-link>
    </nav>
    <router-view />
  </div>
</template>

<script>
export default {
  name: "App"
};
</script>

<style>
#app {
  font-family: Arial, sans-serif;
  max-width: 800px;
  margin: 0 auto;
  padding: 20px;
  font-size: 18px;
}

.nav-links {
  margin-bottom: 20px;
  display: flex;
  justify-content: center;
}

.nav-link {
  text-decoration: none;
  margin-right: 10px;
  color: #333;
  transition: color 0.3s ease-in-out;
}

.nav-link:hover {
  color: #007bff;
  transform: scale(1.1);
}
</style>

<script setup>

</script>

<template>
  <header class="header">
    <div class="container">
      <div class="logo">Appley</div>
      <nav class="nav">
        <a href="#">HOME</a>
        <a href="#">FEATURES</a>
        <a href="#">SERVICES</a>
        <a href="#">PRICING</a>
        <a href="#">SCREENS</a>
        <a href="#">CONTACT</a>
      </nav>
    </div>
  </header>
</template>

<style scoped>
.header {
  background: #ff5ca8;
  padding: 0;
  width: 100%;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: space-between;
  height: 80px;
}

.logo {
  color: #fff;
  font-size: 2.5rem;
  font-weight: bold;
  font-family: 'Montserrat', Arial, sans-serif;
  letter-spacing: 1px;
}

.nav {
  display: flex;
  gap: 32px;
}

.nav a {
  color: #fff;
  text-decoration: none;
  font-size: 1.1rem;
  font-family: 'Montserrat', Arial, sans-serif;
  font-weight: 500;
  transition: opacity 0.2s;
}

.nav a:hover {
  opacity: 0.7;
}
</style>



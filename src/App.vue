<script setup>
import { ref } from 'vue'
const menuOpen = ref(false)
function toggleMenu() { menuOpen.value = !menuOpen.value }
</script>

<template>
  <header class="header">
    <div class="container">
      <!-- Hamburger (mobile only) -->
      <button class="hamburger" @click="toggleMenu" aria-label="Toggle menu">
        <span></span>
        <span></span>
        <span></span>
      </button>
      <!-- Logo always centered -->
      <div class="logo">Appley</div>
    </div>
    <!-- Nav: desktop always visible, mobile toggled -->
    <nav
      class="nav"
      :class="{ open: menuOpen }"
    >
      <a href="#">HOME</a>
      <a href="#">FEATURES</a>
      <a href="#">SERVICES</a>
      <a href="#">PRICING</a>
      <a href="#">SCREENS</a>
      <a href="#">CONTACT</a>
    </nav>
  </header>
</template>

<style scoped>
.header {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  background: #ff5ca8;
  z-index: 1000;
  box-shadow: 0 2px 8px rgba(0,0,0,0.04);
}
.container {
  max-width: 1200px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 80px;
  padding: 0 40px;
  position: relative;
}
.logo {
  color: #fff;
  font-size: 2.5rem;
  font-weight: bold;
  font-family: 'Montserrat', Arial, sans-serif;
  letter-spacing: 1px;
  text-align: center;
  flex: 1;
}
.hamburger {
  display: none;
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 36px;
  height: 36px;
  background: none;
  border: none;
  cursor: pointer;
  position: absolute;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
}
.hamburger span {
  display: block;
  height: 4px;
  width: 100%;
  background: #fff;
  border-radius: 2px;
}
.nav {
  display: flex;
  gap: 32px;
  justify-content: center;
  background: transparent;
  transition: max-height 0.3s, opacity 0.3s;
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

/* Responsive Styles */
@media (max-width: 768px) {
  .container {
    padding: 0 16px;
  }
  .logo {
    font-size: 2rem;
  }
  .nav {
    flex-direction: column;
    gap: 0;
    align-items: flex-start;
    background: #ff5ca8;
    width: 100%;
    max-height: 0;
    overflow: hidden;
    opacity: 0;
    border-top: 1px solid #fff2;
    position: absolute;
    left: 0;
    top: 80px;
    z-index: 999;
  }
  .nav.open {
    max-height: 500px;
    opacity: 1;
    transition: max-height 0.3s, opacity 0.3s;
  }
  .nav a {
    width: 100%;
    padding: 16px 24px;
    border-bottom: 1.5px solid #fff;
    font-size: 1.1rem;
  }
  .hamburger {
    display: flex;
  }
}
</style>



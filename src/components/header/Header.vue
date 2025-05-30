<script setup>
import { ref } from 'vue';
const sidebarOpen = ref(false);
const toggleSidebar = () => { sidebarOpen.value = !sidebarOpen.value; };
const closeSidebar = () => { sidebarOpen.value = false; };
</script>

<template>
  <header class="header">
    <div class="header-content">
      <button
        v-if="!sidebarOpen"
        class="hamburger"
        @click="toggleSidebar"
        aria-label="Open menu"
      >
        <span></span>
        <span></span>
        <span></span>
      </button>
      <button
        v-if="sidebarOpen"
        class="close-header"
        @click="closeSidebar"
        aria-label="Close menu"
      >
        &times;
      </button>
      <div class="logo">Appley</div>
      <!-- Nav only for md and up -->
      <nav class="nav">
        <a href="#">HOME</a>
        <a href="#">FEATURES</a>
        <a href="#">SERVICES</a>
        <a href="#">PRICING</a>
        <a href="#">SCREENS</a>
        <a href="#">CONTACT</a>
      </nav>
    </div>
    <!-- Sidebar for sm only -->
    <div class="sidebar-top" :class="{ open: sidebarOpen }">
      <a href="#" @click="closeSidebar">HOME</a>
      <a href="#" @click="closeSidebar">FEATURES</a>
      <a href="#" @click="closeSidebar">SERVICES</a>
      <a href="#" @click="closeSidebar">PRICING</a>
      <a href="#" @click="closeSidebar">SCREENS</a>
      <a href="#" @click="closeSidebar">CONTACT</a>
    </div>
    <div v-if="sidebarOpen" class="sidebar-backdrop" @click="closeSidebar"></div>
  </header>
</template>

<style scoped>
.header {
  background: #ff5ca8;
  padding: 0;
  border-top: 2px solid #b23a6e;
}
.header-content {
  display: flex;
  align-items: center;
  justify-content: center;
  max-width: 1400px;
  margin: 0 auto;
  height: 90px;
  position: relative;
}
.logo {
  font-size: 48px;
  font-weight: bold;
  color: #fff;
  font-family: 'Montserrat', Arial, sans-serif;
  text-align: center;
  flex: 1;
}
.hamburger,
.close-header {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  z-index: 1201;
  position: absolute;
  left: 16px;
  top: 50%;
  transform: translateY(-50%);
  font-size: 32px;
  color: #fff;
}
.hamburger {
  flex-direction: column;
  justify-content: center;
  gap: 5px;
  width: 40px;
  height: 40px;
}
.hamburger span {
  display: block;
  height: 4px;
  width: 28px;
  background: #fff;
  border-radius: 2px;
  transition: 0.3s;
}
.close-header {
  font-size: 40px;
  font-weight: bold;
  line-height: 1;
}
.nav {
  display: flex;
  gap: 32px;
  margin-right: 40px;
}
.nav a {
  color: #fff;
  text-decoration: none;
  font-weight: 600;
  font-size: 18px;
  letter-spacing: 1px;
  transition: color 0.2s;
}
.nav a:hover {
  color: #b23a6e;
}

.sidebar-top {
  position: fixed;
  top: -100vh;
  left: 0;
  width: 100vw;
  height: 402px;
  background: #ff5ca8;
  color: #fff;
  z-index: 1119;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding-top: 30px;
  transition: top 0.3s;
}
.sidebar-top.open {
  top: 90px; 
}
.sidebar-top a {
  color: #fff;
  text-decoration: none;
  font-weight: 600;
  font-size: 18px;
  padding: 16px 32px;
  border-bottom: 1px solid #fff3;
  width: 100%;
  transition: background 0.2s;
}
.sidebar-top a:hover {
  background: #b23a6e;
}
.sidebar-backdrop {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background: rgba(0,0,0,0.2);
  z-index: 1199;
}

@media (max-width: 768px) {
  .nav {
    display: none;
  }
  .hamburger,
  .close-header {
    display: flex;
  }
  .logo {
    margin-left: 0;
    font-size: 36px;
    text-align: center;
    flex: 1;
  }
  .header-content {
    justify-content: center;
  }
}
@media (min-width: 769px) {
  .sidebar-top,
  .sidebar-backdrop,
  .hamburger,
  .close-header {
    display: none !important;
  }
  .nav {
    display: flex !important;
  }
  .logo {
    margin-left: 30px;
    font-size: 48px;
    text-align: left;
    flex: unset;
  }
  .header-content {
    justify-content: space-between;
  }
}
</style>




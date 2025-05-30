<script setup>
import heroImage from '../assets/iphone.png';
</script>

<template>
  <div class="hero-container">
    <div class="hero-content">
      <h1 class="hero-title">
        The Best Start Up For<br />
        Your Smart App
      </h1>
      <div class="hero-buttons">
        <button class="btn google">
          <span class="icon android"></span>
          Google Play
        </button>
        <button class="btn apple">
          <span class="icon apple"></span>
          Apple IOS
        </button>
      </div>
    </div>
    <div class="hero-image">
      <img :src="heroImage" alt="hero-image" />
    </div>
  </div>
</template>

<style scoped>
.hero-container {
  width: 100%;
  height: 700px;
  background: #8e9092;
  display: flex;
  align-items: center;
  justify-content: center;
  position: relative;
  overflow: hidden;
}

.hero-content {
  flex: 1;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;

}

.hero-title {
  color: #fff;
  font-size: 3rem;
  font-weight: 700;
  margin-bottom: 2.5rem;
  line-height: 1.2;
}

.hero-buttons {
  display: flex;
  gap: 1.5rem;
}

.btn {
  display: flex;
  align-items: center;
  font-size: 1.5rem;
  font-weight: 600;
  border-radius: 4px;
  padding: 1rem 2.5rem;
  border: 2px solid #fff;
  background: transparent;
  color: #fff;
  cursor: pointer;
  transition: 0.2s;
  outline: none;
}

.btn.google {
  background: transparent;
  color: #fff;
  border: 2px solid #fff;
}

.btn.apple {
  background: #ff4fa2;
  color: #fff;
  border: none;
}

.btn .icon {
  display: inline-block;
  margin-right: 1rem;
  font-size: 1.7rem;
}

.icon.android {
  width: 24px;
  height: 24px;
  background: url('https://img.icons8.com/ios-filled/50/fa4fa2/android-os.png') no-repeat center center/contain;
}

.icon.apple {
  width: 24px;
  height: 24px;
  background: url('https://img.icons8.com/ios-filled/50/ffffff/mac-os.png') no-repeat center center/contain;
}

.hero-image {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: center;
 
}

.hero-image img {
  max-height: 600px;
  width: 41.66666667%475px;
  object-fit: contain;
}

@media (max-width: 900px) {
  .hero-container {
    flex-direction: column;
    justify-content: flex-start;
    padding-top: 4rem;
    height: auto;
  }
  .hero-content, .hero-image {
    margin: 0;
    flex: unset;
  }
  .hero-title {
    font-size: 2rem;
  }
  .hero-image img {
    max-height: 300px;
  }
}
</style>

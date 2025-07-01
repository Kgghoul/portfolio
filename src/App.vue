<script setup>
import { RouterLink, RouterView } from 'vue-router'
import { ref, provide } from 'vue'
import powerIcon from '@/assets/power.png'

const isEnglish = ref(false)

const translations = {
  ru: {
    home: 'Главная',
    about: 'О нас'
  },
  en: {
    home: 'Home',
    about: 'About Us'
  }
}

const toggleLanguage = () => {
  isEnglish.value = !isEnglish.value
}

provide('language', {
  isEnglish,
  translations,
  toggleLanguage
})
</script>

<template>
  <div id="app">
    <nav class="navbar">
      <div class="nav-container">
        <div class="nav-logo">
          <h2>
            <img :src="powerIcon" alt="Power" class="logo-icon">
            Portfolio
          </h2>
        </div>
        <div class="nav-menu">
          <div class="btn-container">
            <div class="btn-color-mode-switch">
              <input type="checkbox" id="color_mode" name="color_mode" value="1" @change="toggleLanguage" :checked="isEnglish">
              <label for="color_mode" class="btn-color-mode-switch-inner" data-off="RU" data-on="EN"></label>
            </div>
          </div>
          <RouterLink to="/" class="button">{{ isEnglish ? translations.en.home : translations.ru.home }}</RouterLink>
          <RouterLink to="/gallery" class="button">{{ isEnglish ? translations.en.about : translations.ru.about }}</RouterLink>
        </div>
      </div>
    </nav>
    
    <main>
      <RouterView />
    </main>
    </div>
</template>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
  line-height: 1.6;
  color: #333;
  background: #fafafa;
  overflow-x: hidden;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

#app {
  width: 100vw;
  overflow-x: hidden;
}

main {
  width: 100vw;
  overflow-x: hidden;
}

.navbar {
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(20px);
  box-shadow: 0 8px 32px rgba(0,0,0,0.06);
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  z-index: 1000;
  border-bottom: 1px solid rgba(0, 212, 255, 0.1);
  transition: all 0.3s ease;
}

.navbar:hover {
  background: rgba(255, 255, 255, 0.95);
  box-shadow: 0 12px 40px rgba(0,0,0,0.08);
}

.nav-container {
  max-width: 1300px;
  margin: 0 auto;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1.2rem 2.5rem;
}

.nav-logo h2 {
  background: linear-gradient(135deg, #00d4ff 0%, #ff6b35 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  font-weight: 800;
  font-size: 1.8rem;
  letter-spacing: -0.5px;
  position: relative;
}

.nav-logo h2::after {
  content: '';
  position: absolute;
  bottom: -2px;
  left: 0;
  width: 30%;
  height: 3px;
  background: linear-gradient(90deg, #00d4ff, transparent);
  border-radius: 2px;
}

.logo-icon {
  height: 1.8rem;
  width: auto;
  margin-right: 0.5rem;
  display: inline-block;
  vertical-align: middle;
  filter: drop-shadow(0 0 4px rgba(0, 212, 255, 0.3));
  transition: all 0.3s ease;
  object-fit: contain;
}

.nav-logo:hover .logo-icon {
  filter: drop-shadow(0 0 6px rgba(0, 212, 255, 0.5));
  transform: scale(1.05);
}



.nav-menu {
  display: flex;
  gap: 1rem;
  align-items: center;
}

.button {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background: rgba(255, 255, 255, 0.1);
  color: #333;
  font-size: 13px;
  font-weight: 600;
  border: 1px solid rgba(0, 0, 0, 0.1);
  padding: 12px 20px;
  border-radius: 12px;
  cursor: pointer;
  transition: all 0.3s ease;
  text-decoration: none;
  backdrop-filter: blur(10px);
}

.button:hover {
  background: rgba(255, 255, 255, 0.2);
  border-color: rgba(0, 212, 255, 0.3);
  transform: translateY(-1px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.button:active {
  transform: translateY(0);
  box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.button.router-link-active {
  background: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
  color: white;
  border-color: rgba(255, 255, 255, 0.3);
  box-shadow: 0 4px 12px rgba(0, 212, 255, 0.3);
}

.button:focus {
  outline: none;
}

/* From Uiverse.io by JaydipPrajapati1910 */ 
.btn-container {
  display: table-cell;
  vertical-align: middle;
  text-align: center;
}

.btn-color-mode-switch {
  display: inline-block;
  margin: 0px;
  position: relative;
}

.btn-color-mode-switch > label.btn-color-mode-switch-inner {
  margin: 0px;
  width: 140px;
  height: 40px;
  background: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
  border-radius: 24px;
  overflow: hidden;
  position: relative;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 
    0 4px 15px rgba(0, 212, 255, 0.3),
    0 2px 8px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.2);
  display: block;
  cursor: pointer;
  border: 1px solid rgba(255, 255, 255, 0.2);
  backdrop-filter: blur(10px);
}

.btn-color-mode-switch > label.btn-color-mode-switch-inner:hover {
  transform: translateY(-2px);
  box-shadow: 
    0 6px 20px rgba(0, 212, 255, 0.4),
    0 4px 12px rgba(0, 0, 0, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.3);
}

.btn-color-mode-switch > label.btn-color-mode-switch-inner:before {
  content: attr(data-on);
  position: absolute;
  font-size: 16px;
  font-weight: 700;
  top: 50%;
  transform: translateY(-50%);
  right: 20px;
  color: rgba(255, 255, 255, 0.9);
  letter-spacing: 0.5px;
  transition: all 0.3s ease;
}

.btn-color-mode-switch > label.btn-color-mode-switch-inner:after {
  content: attr(data-off);
  width: 66px;
  height: 32px;
  background: linear-gradient(135deg, #ffffff 0%, #f8f9fa 100%);
  border-radius: 20px;
  position: absolute;
  font-size: 16px;
  display: flex;
  justify-content: center;
  align-items: center;
  left: 4px;
  top: 4px;
  text-align: center;
  transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
  box-shadow: 
    0 4px 12px rgba(0, 0, 0, 0.15),
    0 2px 4px rgba(0, 0, 0, 0.1),
    inset 0 1px 0 rgba(255, 255, 255, 0.8);
  color: #0099cc;
  font-weight: 700;
  letter-spacing: 0.5px;
  border: 1px solid rgba(0, 153, 204, 0.1);
}

.btn-color-mode-switch input[type="checkbox"] {
  cursor: pointer;
  width: 50px;
  height: 25px;
  opacity: 0;
  position: absolute;
  top: 0;
  z-index: 1;
  margin: 0px;
}

.btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner {
  background: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
}

.btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner:after {
  content: attr(data-on);
  left: 70px;
  transform: scale(1.05);
  box-shadow: 
    0 6px 16px rgba(0, 0, 0, 0.2),
    0 3px 6px rgba(0, 0, 0, 0.15),
    inset 0 1px 0 rgba(255, 255, 255, 0.9);
}

.btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner:before {
  content: attr(data-off);
  right: auto;
  left: 20px;
  transform: translateY(-50%);
}

@media (max-width: 768px) {
  .nav-container {
    padding: 0.8rem 1rem;
    flex-wrap: wrap;
  }
  
  .nav-logo h2 {
    font-size: 1.4rem;
  }
  
  .logo-icon {
    height: 1.4rem;
    margin-right: 0.3rem;
  }
  
  .nav-menu {
    gap: 0.8rem;
    flex-wrap: wrap;
    justify-content: center;
    width: 100%;
    margin-top: 0.5rem;
  }
  
  .btn-color-mode-switch > label.btn-color-mode-switch-inner {
    width: 110px;
    height: 32px;
  }
  
  .btn-color-mode-switch > label.btn-color-mode-switch-inner:before {
    font-size: 13px;
    right: 12px;
  }
  
  .btn-color-mode-switch > label.btn-color-mode-switch-inner:after {
    width: 52px;
    height: 24px;
    font-size: 13px;
    left: 4px;
    top: 4px;
  }
  
  .btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner:after {
    left: 54px;
  }
  
  .button {
    font-size: 13px;
    padding: 10px 18px;
    border-radius: 16px;
  }
}

@media (max-width: 480px) {
  .nav-container {
    padding: 0.7rem 0.8rem;
    flex-direction: column;
    gap: 0.8rem;
  }
  
  .nav-logo h2 {
    font-size: 1.3rem;
    text-align: center;
  }
  
  .logo-icon {
    height: 1.3rem;
    margin-right: 0.3rem;
  }
  
  .nav-menu {
    gap: 0.8rem;
    justify-content: center;
    width: 100%;
    margin-top: 0;
  }
  
  .btn-color-mode-switch > label.btn-color-mode-switch-inner {
    width: 95px;
    height: 28px;
  }
  
  .btn-color-mode-switch > label.btn-color-mode-switch-inner:before {
    font-size: 12px;
    right: 10px;
  }
  
  .btn-color-mode-switch > label.btn-color-mode-switch-inner:after {
    width: 44px;
    height: 20px;
    font-size: 12px;
    left: 4px;
    top: 4px;
  }
  
  .btn-color-mode-switch input[type="checkbox"]:checked + label.btn-color-mode-switch-inner:after {
    left: 47px;
  }
  
  .button {
    font-size: 12px;
    padding: 10px 16px;
    border-radius: 14px;
    min-width: 80px;
  }
}
</style>
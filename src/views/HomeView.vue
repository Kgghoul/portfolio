<script setup>
import { inject } from 'vue'
// Background image is loaded via CSS url()

const { isEnglish } = inject('language')

const translations = {
  ru: {
    title: 'Создаем современные',
    titleAccent: 'веб-решения',
    subtitle: 'Команда из двух фриланс-разработчиков с опытом создания качественных сайтов и веб-приложений. Превращаем ваши идеи в функциональные и красивые цифровые продукты.',
    button: 'О нас',
    workExample: 'пример работы',
    projectDesc: 'Платформа для улучшения промтов с использованием искусственного интеллекта',
    visitProject: 'Посетить проект'
  },
  en: {
    title: 'Creating modern',
    titleAccent: 'web solutions',
    subtitle: 'A team of two freelance developers with experience in creating high-quality websites and web applications. We turn your ideas into functional and beautiful digital products.',
    button: 'About Us',
    workExample: 'work example',
    projectDesc: 'Platform for improving prompts using artificial intelligence',
    visitProject: 'Visit Project'
  }
}
</script>

<template>
  <div class="home">
    <section class="hero">
      <div class="hero-content">
        <div class="hero-text">
          <h1 class="hero-title">
            {{ isEnglish ? translations.en.title : translations.ru.title }}
            <span class="gradient-text">{{ isEnglish ? translations.en.titleAccent : translations.ru.titleAccent }}</span>
          </h1>
          <p class="hero-subtitle">
            {{ isEnglish ? translations.en.subtitle : translations.ru.subtitle }}
          </p>
          <div class="hero-buttons">
            <RouterLink to="/gallery" class="outer-btn">
              <div class="inner-btn">
                <span class="btn-text">{{ isEnglish ? translations.en.button : translations.ru.button }}</span>
              </div>
            </RouterLink>
          </div>
        </div>
        <div class="hero-image">
          <a href="https://daniilzaj.github.io/RefinedAI/" target="_blank" class="project-card">
            <span class="work-example">{{ isEnglish ? translations.en.workExample : translations.ru.workExample }}</span>
            <div class="align">
              <div class="red"></div>
              <div class="yellow"></div>
              <div class="green"></div>
            </div>
            <div class="card-content">
              <h3>RefinedAI</h3>
              <p class="project-url">daniilzaj.github.io</p>
              <div class="project-description">
                <span class="project-tech">Vue.js</span>
                <span class="project-tech">Go</span>
              </div>
              <div class="hover-content">
                <p>{{ isEnglish ? translations.en.projectDesc : translations.ru.projectDesc }}</p>
                <div class="visit-button">
                  <span>{{ isEnglish ? translations.en.visitProject : translations.ru.visitProject }}</span>
                </div>
              </div>
            </div>
          </a>
        </div>
      </div>
    </section>
    </div>
</template>

<style scoped>
.home {
  min-height: 100vh;
  width: 100vw;
  margin: 0;
  padding: 0;
  overflow-x: hidden;
}

.container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
}

.hero {
  background-image: 
    linear-gradient(135deg, rgba(0, 0, 0, 0.3) 0%, rgba(0, 0, 0, 0.7) 100%),
    url('@/assets/dark_workspace_developer_background.webp');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  min-height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  color: white;
  position: relative;
  overflow-x: hidden;
}

.hero::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: radial-gradient(circle at 30% 50%, rgba(0, 212, 255, 0.1) 0%, transparent 50%);
  z-index: 0;
}

.hero-content {
  max-width: 1300px;
  margin: 0 auto;
  padding: 3rem;
  display: grid;
  grid-template-columns: 1.2fr 1fr;
  gap: 5rem;
  align-items: center;
  position: relative;
  z-index: 1;
  animation: slideInUp 1s ease-out;
}

@keyframes slideInUp {
  from {
    transform: translateY(30px);
  }
  to {
    transform: translateY(0);
  }
}

.hero-title {
  font-size: 4rem;
  font-weight: 900;
  line-height: 1.1;
  margin-bottom: 1.5rem;
  text-shadow: 2px 2px 4px rgba(0,0,0,0.3);
}

.gradient-text {
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  position: relative;
  white-space: nowrap;
}

.hero-subtitle {
  font-size: 1.3rem;
  line-height: 1.7;
  margin-bottom: 2.5rem;
  opacity: 1;
  font-weight: 500;
  max-width: 500px;
  text-shadow: 2px 2px 8px rgba(0, 0, 0, 0.7), 1px 1px 4px rgba(0, 0, 0, 0.5);
  color: rgba(255, 255, 255, 0.95);
}

.hero-buttons {
  display: flex;
  gap: 1rem;
}

.outer-btn {
  display: inline-flex;
  align-items: center;
  justify-content: center;
  background: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
  color: white;
  padding: 1rem 2rem;
  border-radius: 12px;
  text-decoration: none;
  font-size: 16px;
  font-weight: 600;
  transition: all 0.3s ease;
  border: none;
  cursor: pointer;
}

.outer-btn:hover {
  background: linear-gradient(135deg, #0099cc 0%, #007acc 100%);
  transform: translateY(-2px);
  box-shadow: 0 8px 25px rgba(0, 212, 255, 0.3);
}

.inner-btn {
  display: flex;
  align-items: center;
  gap: 0.5rem;
}

.btn-text {
  font-size: 16px;
  font-weight: 600;
  color: white;
}

.hero-image {
  display: flex;
  justify-content: center;
}

.project-card {
  width: 420px;
  height: 280px;
  padding: 0.8rem;
  background: rgba(255, 255, 255, 0.15);
  border-radius: 16px;
  backdrop-filter: blur(20px);
  border-bottom: 4px solid rgba(0, 212, 255, 0.3);
  border-left: 3px rgba(255, 255, 255, 0.4) outset;
  box-shadow: -30px 40px 50px rgba(0, 0, 0, 0.3);
  transform: skewX(8deg);
  transition: all 0.5s ease;
  overflow: hidden;
  color: white;
  text-decoration: none;
  position: relative;
  cursor: pointer;
}

.project-card:hover {
  height: 400px;
  transform: skew(0deg) scale(1.02);
  box-shadow: -40px 60px 80px rgba(0, 0, 0, 0.4);
  background: rgba(255, 255, 255, 0.2);
}

.align {
  padding: 1rem;
  display: flex;
  flex-direction: row;
  gap: 8px;
  align-self: flex-start;
}

.red {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #ff605c;
  box-shadow: -3px 3px 6px rgba(0, 0, 0, 0.3);
}

.yellow {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #ffbd44;
  box-shadow: -3px 3px 6px rgba(0, 0, 0, 0.3);
}

.green {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #00ca4e;
  box-shadow: -3px 3px 6px rgba(0, 0, 0, 0.3);
}

.card-content {
  padding: 1rem 1.5rem;
  text-align: center;
}

.card-content h3 {
  font-size: 2rem;
  font-weight: 800;
  margin-bottom: 0.8rem;
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  text-shadow: none;
}

.project-url {
  font-size: 0.9rem;
  opacity: 0.8;
  margin-bottom: 1.5rem;
  font-family: 'Courier New', monospace;
  background: rgba(0, 0, 0, 0.2);
  padding: 0.3rem 0.8rem;
  border-radius: 20px;
  display: inline-block;
}

.project-description {
  display: flex;
  flex-wrap: wrap;
  gap: 0.5rem;
  justify-content: center;
  margin-bottom: 1rem;
}

.project-tech {
  background: rgba(0, 212, 255, 0.2);
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
  border: 1px solid rgba(0, 212, 255, 0.3);
}

.hover-content {
  opacity: 0;
  transform: translateY(20px);
  transition: all 0.4s ease;
  margin-top: 1rem;
}

.project-card:hover .hover-content {
  opacity: 1;
  transform: translateY(0);
}

.hover-content p {
  font-size: 0.95rem;
  line-height: 1.6;
  margin-bottom: 1.5rem;
  opacity: 0.9;
}

.visit-button {
  background: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
  padding: 0.8rem 1.5rem;
  border-radius: 12px;
  font-weight: 600;
  box-shadow: 0 8px 20px rgba(0, 212, 255, 0.3);
  transition: all 0.3s ease;
  display: inline-block;
}

.visit-button:hover {
  transform: translateY(-2px);
  box-shadow: 0 12px 30px rgba(0, 212, 255, 0.4);
}

.work-example {
  position: absolute;
  top: 1rem;
  right: 1.5rem;
  font-size: 0.8rem;
  color: rgba(255, 255, 255, 0.7);
  font-weight: 500;
}

@media (max-width: 768px) {
  .hero {
    background-attachment: scroll;
    min-height: 100vh;
    width: 100vw;
    padding: 1rem 0;
  }
  
  .hero-content {
    grid-template-columns: 1fr;
    text-align: center;
    gap: 3rem;
    padding: 2rem 1.5rem;
    max-width: 100%;
    margin-top: 9rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-title {
    font-size: 2.8rem;
    margin-bottom: 1.5rem;
    line-height: 1.2;
  }
  
  .hero-subtitle {
    font-size: 1.2rem;
    max-width: 100%;
    margin-bottom: 2.5rem;
    line-height: 1.7;
    padding: 0 1rem;
  }
  
  .project-card {
    width: min(85vw, 420px);
    height: 320px;
    transform: skewX(2deg);
    margin: 0 auto;
  }
  
  .project-card:hover {
    height: 420px;
    transform: skew(0deg) scale(1.02);
  }
  
  .card-content {
    padding: 1rem 1.5rem;
  }
  
  .card-content h3 {
    font-size: 2rem;
    margin-bottom: 0.8rem;
  }
  
  .project-url {
    font-size: 0.9rem;
    margin-bottom: 1.5rem;
  }
  
  .project-tech {
    font-size: 0.8rem;
    padding: 0.3rem 0.8rem;
  }
  
  .hover-content p {
    font-size: 1rem;
    margin-bottom: 1.5rem;
  }
  
  .visit-button {
    padding: 0.8rem 1.5rem;
    font-size: 1rem;
  }
  
  .outer-btn {
    padding: 1.2rem 2.5rem;
    font-size: 18px;
    border-radius: 16px;
  }
}

@media (max-width: 600px) {
  .hero-content {
    gap: 2.5rem;
    padding: 1.5rem 1rem;
    margin-top: 5.5rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-title {
    font-size: 2.4rem;
    margin-bottom: 1.2rem;
  }
  
  .hero-subtitle {
    font-size: 1.1rem;
    padding: 0 0.5rem;
    margin-bottom: 2rem;
  }
  
  .project-card {
    width: min(90vw, 380px);
    height: 300px;
    transform: skewX(1deg);
  }
  
  .project-card:hover {
    height: 400px;
    transform: skew(0deg) scale(1.01);
  }
  
  .card-content {
    padding: 0.8rem 1.2rem;
  }
  
  .card-content h3 {
    font-size: 1.8rem;
    margin-bottom: 0.6rem;
  }
  
  .project-url {
    font-size: 0.85rem;
    margin-bottom: 1.2rem;
  }
  
  .project-tech {
    font-size: 0.75rem;
    padding: 0.25rem 0.7rem;
  }
  
  .hover-content p {
    font-size: 0.95rem;
    margin-bottom: 1.2rem;
  }
  
  .visit-button {
    padding: 0.7rem 1.3rem;
    font-size: 0.95rem;
  }
  
  .outer-btn {
    padding: 1rem 2rem;
    font-size: 16px;
  }
}

@media (max-width: 480px) {
  .hero {
    padding: 0.5rem 0;
  }
  
  .hero-content {
    padding: 1rem 0.8rem;
    gap: 2rem;
    margin-top: 5rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-title {
    font-size: 2rem;
    margin-bottom: 1rem;
  }
  
  .hero-subtitle {
    font-size: 1rem;
    padding: 0 0.3rem;
    line-height: 1.6;
    margin-bottom: 1.8rem;
  }
  
  .project-card {
    width: min(95vw, 340px);
    height: 280px;
    transform: skewX(1deg);
  }
  
  .project-card:hover {
    height: 380px;
    transform: skew(0deg) scale(1.01);
  }
  
  .card-content {
    padding: 0.7rem 1rem;
  }
  
  .card-content h3 {
    font-size: 1.6rem;
    margin-bottom: 0.5rem;
  }
  
  .project-url {
    font-size: 0.8rem;
    margin-bottom: 1rem;
  }
  
  .project-tech {
    font-size: 0.7rem;
    padding: 0.2rem 0.6rem;
  }
  
  .hover-content p {
    font-size: 0.9rem;
    margin-bottom: 1rem;
  }
  
  .visit-button {
    padding: 0.6rem 1.2rem;
    font-size: 0.9rem;
  }
  
  .work-example {
    font-size: 0.75rem;
    top: 0.8rem;
    right: 1rem;
  }
  
  .outer-btn {
    padding: 0.9rem 1.8rem;
    font-size: 15px;
    border-radius: 14px;
  }
}

@media (max-width: 360px) {
  .hero-content {
    padding: 0.8rem 0.5rem;
    gap: 1.8rem;
    margin-top: 6.5rem;
  }
  
  .hero-buttons {
    justify-content: center;
  }
  
  .hero-title {
    font-size: 1.8rem;
    margin-bottom: 0.8rem;
  }
  
  .hero-subtitle {
    font-size: 0.95rem;
    padding: 0 0.2rem;
    line-height: 1.5;
    margin-bottom: 1.5rem;
  }
  
  .project-card {
    width: min(98vw, 320px);
    height: 260px;
  }
  
  .project-card:hover {
    height: 360px;
  }
  
  .card-content {
    padding: 0.6rem 0.8rem;
  }
  
  .card-content h3 {
    font-size: 1.4rem;
    margin-bottom: 0.4rem;
  }
  
  .project-url {
    font-size: 0.75rem;
    margin-bottom: 0.8rem;
  }
  
  .project-tech {
    font-size: 0.65rem;
    padding: 0.15rem 0.5rem;
  }
  
  .hover-content p {
    font-size: 0.85rem;
    margin-bottom: 0.8rem;
  }
  
  .visit-button {
    padding: 0.5rem 1rem;
    font-size: 0.85rem;
  }
  
  .work-example {
    font-size: 0.7rem;
    top: 0.6rem;
    right: 0.8rem;
  }
  
  .outer-btn {
    padding: 0.8rem 1.5rem;
    font-size: 14px;
  }
}
</style>

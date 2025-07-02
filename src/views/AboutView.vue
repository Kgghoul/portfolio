<script setup>
import { inject } from 'vue'
import frontendIcon from '@/assets/user-experience.png'
import backendIcon from '@/assets/software.png'
// Background image is loaded via CSS url()

const { isEnglish } = inject('language')

const translations = {
  ru: {
    aboutTitle: 'О',
    aboutTitleAccent: 'нас',
    aboutDesc: 'Команда из двух фриланс-разработчиков с 6+ месяцами опыта создания веб-сайтов. Фронтенд на Vue.js и бэкенд на Go - полный цикл разработки.',
    skillsTitle: 'Наш стек',
    servicesTitle: 'Тарифы',
    lite: {
      title: 'Lite',
      time: '1-3 дня',
      price: '$80',
      features: ['1-2 страницы', 'Лендинг/визитка']
    },
    standard: {
      title: 'Standard',
      time: '5-7 дней',
      price: '$120',
      features: ['4 страницы', 'Сайт для бизнеса', 'Интеграция ИИ', 'Автоответчик']
    },
    premium: {
      title: 'Premium',
      time: '14 дней',
      price: '$250',
      features: ['7 страниц', 'Полноценный сайт', 'Интеграция ИИ', 'Админ панель', 'Аналитика', 'Установка на сервер']
    },
    bestProject: 'Лучший проект',
    projectDesc: 'Платформа для улучшения промтов с ИИ',
    contacts: 'Контакты',
    frontendDev: 'Frontend',
    frontendDevSub: 'Разработчик',
    backendDev: 'Backend',
    backendDevSub: 'Разработчик'
  },
  en: {
    aboutTitle: 'About',
    aboutTitleAccent: 'Us',
    aboutDesc: 'A team of two freelance developers with 6+ months of experience creating websites. Frontend on Vue.js and backend on Go - full development cycle.',
    skillsTitle: 'Our Stack',
    servicesTitle: 'Pricing',
    lite: {
      title: 'Lite',
      time: '1-3 days',
      price: '$80',
      features: ['1-2 pages', 'Landing/Business card']
    },
    standard: {
      title: 'Standard',
      time: '5-7 days',
      price: '$120',
      features: ['4 pages', 'Business website', 'AI Integration', 'Auto-responder']
    },
    premium: {
      title: 'Premium',
      time: '14 days',
      price: '$250',
      features: ['7 pages', 'Full-featured website', 'AI Integration', 'Admin panel', 'Analytics', 'Server deployment']
    },
    bestProject: 'Best Project',
    projectDesc: 'Platform for improving prompts with AI',
    contacts: 'Contacts',
    frontendDev: 'Frontend',
    frontendDevSub: 'Developer',
    backendDev: 'Backend',
    backendDevSub: 'Developer'
  }
}
</script>

<template>
  <div class="about">
    <div class="about-content">
      <div class="left-section">
        <div class="about-info">
          <h1 class="about-title">
            {{ isEnglish ? translations.en.aboutTitle : translations.ru.aboutTitle }} <span class="gradient-text">{{ isEnglish ? translations.en.aboutTitleAccent : translations.ru.aboutTitleAccent }}</span>
          </h1>
          <p class="about-description">
            {{ isEnglish ? translations.en.aboutDesc : translations.ru.aboutDesc }}
          </p><div class="skills-section"><h3>{{ isEnglish ? translations.en.skillsTitle : translations.ru.skillsTitle }}</h3>
            <div class="skills-grid">
              <div class="keycap">
                <div class="letter">Vue.js</div>
              </div>
              <div class="keycap">
                <div class="letter">Go</div>
              </div>
              <div class="keycap">
                <div class="letter">TS</div>
              </div>
              <div class="keycap">
                <div class="letter">SQL</div>
              </div>
              <div class="keycap">
                <div class="letter">Docker</div>
              </div>
              <div class="keycap">
                <div class="letter">Git</div>
              </div>
            </div>
          </div>
          <div class="services-section">
            <h3>{{ isEnglish ? translations.en.servicesTitle : translations.ru.servicesTitle }}</h3>
            <div class="pricing-cards">
                              <div class="card">
                  <div class="card-img lite-bg"></div>
                  <div class="card-info">
                    <p class="text-title">{{ isEnglish ? translations.en.lite.title : translations.ru.lite.title }}</p>
                    <p class="text-body">{{ isEnglish ? translations.en.lite.time : translations.ru.lite.time }}</p>
                    <div class="check-list">
                      <div class="check-list-item" v-for="feature in (isEnglish ? translations.en.lite.features : translations.ru.lite.features)" :key="feature">
                        <span>✓</span> {{ feature }}
                      </div>
                    </div>
                  </div>
                  <div class="card-footer">
                    <span class="text-title">{{ isEnglish ? translations.en.lite.price : translations.ru.lite.price }}</span>
                  </div>
                </div>
                              <div class="card">
                  <div class="card-img standard-bg"></div>
                  <div class="card-info">
                    <p class="text-title">{{ isEnglish ? translations.en.standard.title : translations.ru.standard.title }}</p>
                    <p class="text-body">{{ isEnglish ? translations.en.standard.time : translations.ru.standard.time }}</p>
                    <div class="check-list">
                      <div class="check-list-item" v-for="feature in (isEnglish ? translations.en.standard.features : translations.ru.standard.features)" :key="feature">
                        <span>✓</span> {{ feature }}
                      </div>
                    </div>
                  </div>
                  <div class="card-footer">
                    <span class="text-title">{{ isEnglish ? translations.en.standard.price : translations.ru.standard.price }}</span>
                  </div>
                </div>
                              <div class="card">
                  <div class="card-img premium-bg"></div>
                  <div class="card-info">
                    <p class="text-title">{{ isEnglish ? translations.en.premium.title : translations.ru.premium.title }}</p>
                    <p class="text-body">{{ isEnglish ? translations.en.premium.time : translations.ru.premium.time }}</p>
                    <div class="check-list">
                      <div class="check-list-item" v-for="feature in (isEnglish ? translations.en.premium.features : translations.ru.premium.features)" :key="feature">
                        <span>✓</span> {{ feature }}
                      </div>
                    </div>
                  </div>
                  <div class="card-footer">
                    <span class="text-title">{{ isEnglish ? translations.en.premium.price : translations.ru.premium.price }}</span>
                  </div>
                </div>
            </div>
          </div>
        </div>
      </div>
      <div class="right-section">
        <div class="featured-project">
          <h3>{{ isEnglish ? translations.en.bestProject : translations.ru.bestProject }}</h3>
          <a href="https://daniilzaj.github.io/RefinedAI/" target="_blank" class="project-showcase">
            <div class="browser-header">
              <div class="browser-buttons">
                <div class="red"></div>
                <div class="yellow"></div>
                <div class="green"></div>
              </div>
              <span class="browser-url">daniilzaj.github.io</span>
            </div>
            <div class="project-info">
              <h4 class="project-name">RefinedAI</h4>
              <p class="project-desc">{{ isEnglish ? translations.en.projectDesc : translations.ru.projectDesc }}</p>
              <div class="project-tech">
                <span>Vue.js</span>
                <span>Go</span>
              </div>
            </div>
          </a>
        </div>
        <div class="contact-section">
          <h3>{{ isEnglish ? translations.en.contacts : translations.ru.contacts }}</h3>
          <div class="team-contacts">
            <div class="developer-card">
              <div class="dev-info">
                <div class="dev-avatar">
                  <img :src="frontendIcon" alt="Frontend Developer" class="dev-icon">
                </div>
                <h4 class="dev-name">
                  {{ isEnglish ? translations.en.frontendDev : translations.ru.frontendDev }}<br>
                  <span class="dev-subtitle">{{ isEnglish ? translations.en.frontendDevSub : translations.ru.frontendDevSub }}</span>
                </h4>
                <p class="dev-role">Vue.js • JavaScript • UI/UX</p>
              </div>
              <div class="dev-contacts">
                <div class="contact-item">
                  <a href="https://www.linkedin.com/in/karim-kassymkhanov-b753b8372" target="_blank" data-social="linkedin">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-linkedin" viewBox="0 0 16 16">
                      <path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854zm4.943 12.248V6.169H2.542v7.225zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248S2.4 3.226 2.4 3.934c0 .694.521 1.248 1.327 1.248zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016l.016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225z"/>
                    </svg>
                    <span class="contact-tooltip">LinkedIn</span>
                  </a>
                </div>
                <div class="contact-item">
                  <a href="https://github.com/Kgghoul" target="_blank" data-social="github">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
                    </svg>
                    <span class="contact-tooltip">GitHub</span>
                  </a>
                </div>
                <div class="contact-item">
                  <a href="mailto:daniilkarimtech@gmail.com" data-social="email">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-envelope" viewBox="0 0 16 16">
                      <path d="M0 4a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2zm2-1a1 1 0 0 0-1 1v.217l7 4.2 7-4.2V4a1 1 0 0 0-1-1zm13 2.383-4.708 2.825L15 11.105zm-.034 6.876-5.64-3.471L8 9.583l-1.326-.795-5.64 3.47A1 1 0 0 0 2 13h12a1 1 0 0 0 .966-.741M1 11.105l4.708-2.897L1 5.383z"/>
                    </svg>
                    <span class="contact-tooltip">Email</span>
                  </a>
                </div>
                <div class="contact-item">
                  <a href="https://t.me/nextgeneng" target="_blank" data-social="telegram">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-telegram" viewBox="0 0 16 16">
                      <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M8.287 5.906q-1.168.486-4.666 2.01-.567.225-.595.442c-.03.243.275.339.69.47l.175.055c.408.133.958.288 1.243.294q.39.01.868-.32 3.269-2.206 3.374-2.23c.05-.012.12-.026.166.016s.042.12.037.141c-.03.129-1.227 1.241-1.846 1.817-.193.18-.33.307-.358.336a8 8 0 0 1-.188.186c-.38.366-.664.64.015 1.088.327.216.589.393.85.571.284.194.568.387.936.629q.14.092.27.187c.331.236.63.448.997.414.214-.02.435-.22.547-.82.265-1.417.786-4.486.906-5.751a1.4 1.4 0 0 0-.013-.315.34.34 0 0 0-.114-.217.53.53 0 0 0-.31-.093c-.3.005-.763.166-2.984 1.09"/>
                    </svg>
                    <span class="contact-tooltip">Telegram</span>
                  </a>
                </div>
              </div>
            </div>

            <div class="developer-card">
              <div class="dev-info">
                <div class="dev-avatar">
                  <img :src="backendIcon" alt="Backend Developer" class="dev-icon">
                </div>
                <h4 class="dev-name">
                  {{ isEnglish ? translations.en.backendDev : translations.ru.backendDev }}<br>
                  <span class="dev-subtitle">{{ isEnglish ? translations.en.backendDevSub : translations.ru.backendDevSub }}</span>
                </h4>
                <p class="dev-role">Go • PostgreSQL • Docker</p>
              </div>
              <div class="dev-contacts">
                <div class="contact-item">
                  <a href="https://www.linkedin.com/in/daniil-z-6331a1346?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=ios_app" target="_blank" data-social="linkedin">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-linkedin" viewBox="0 0 16 16">
                      <path d="M0 1.146C0 .513.526 0 1.175 0h13.65C15.474 0 16 .513 16 1.146v13.708c0 .633-.526 1.146-1.175 1.146H1.175C.526 16 0 15.487 0 14.854zm4.943 12.248V6.169H2.542v7.225zm-1.2-8.212c.837 0 1.358-.554 1.358-1.248-.015-.709-.52-1.248-1.342-1.248S2.4 3.226 2.4 3.934c0 .694.521 1.248 1.327 1.248zm4.908 8.212V9.359c0-.216.016-.432.08-.586.173-.431.568-.878 1.232-.878.869 0 1.216.662 1.216 1.634v3.865h2.401V9.25c0-2.22-1.184-3.252-2.764-3.252-1.274 0-1.845.7-2.165 1.193v.025h-.016l.016-.025V6.169h-2.4c.03.678 0 7.225 0 7.225z"/>
                    </svg>
                    <span class="contact-tooltip">LinkedIn</span>
                  </a>
                </div>
                <div class="contact-item">
                  <a href="https://github.com/daniilzaj" target="_blank" data-social="github">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-github" viewBox="0 0 16 16">
                      <path d="M8 0C3.58 0 0 3.58 0 8c0 3.54 2.29 6.53 5.47 7.59.4.07.55-.17.55-.38 0-.19-.01-.82-.01-1.49-2.01.37-2.53-.49-2.69-.94-.09-.23-.48-.94-.82-1.13-.28-.15-.68-.52-.01-.53.63-.01 1.08.58 1.23.82.72 1.21 1.87.87 2.33.66.07-.52.28-.87.51-1.07-1.78-.2-3.64-.89-3.64-3.95 0-.87.31-1.59.82-2.15-.08-.2-.36-1.02.08-2.12 0 0 .67-.21 2.2.82.64-.18 1.32-.27 2-.27s1.36.09 2 .27c1.53-1.04 2.2-.82 2.2-.82.44 1.1.16 1.92.08 2.12.51.56.82 1.27.82 2.15 0 3.07-1.87 3.75-3.65 3.95.29.25.54.73.54 1.48 0 1.07-.01 1.93-.01 2.2 0 .21.15.46.55.38A8.01 8.01 0 0 0 16 8c0-4.42-3.58-8-8-8"/>
                    </svg>
                    <span class="contact-tooltip">GitHub</span>
                  </a>
                </div>
                <div class="contact-item">
                  <a href="mailto:daniilkarimtech@gmail.com" data-social="email">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-envelope" viewBox="0 0 16 16">
                      <path d="M0 4a2 2 0 0 1 2-2h12a2 2 0 0 1 2 2v8a2 2 0 0 1-2 2H2a2 2 0 0 1-2-2zm2-1a1 1 0 0 0-1 1v.217l7 4.2 7-4.2V4a1 1 0 0 0-1-1zm13 2.383-4.708 2.825L15 11.105zm-.034 6.876-5.64-3.471L8 9.583l-1.326-.795-5.64 3.47A1 1 0 0 0 2 13h12a1 1 0 0 0 .966-.741M1 11.105l4.708-2.897L1 5.383z"/>
                    </svg>
                    <span class="contact-tooltip">Email</span>
                  </a>
                </div>
                <div class="contact-item">
                  <a href="https://t.me/dnlzjfrt" target="_blank" data-social="telegram">
                    <div class="contact-filled"></div>
                    <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-telegram" viewBox="0 0 16 16">
                      <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M8.287 5.906q-1.168.486-4.666 2.01-.567.225-.595.442c-.03.243.275.339.69.47l.175.055c.408.133.958.288 1.243.294q.39.01.868-.32 3.269-2.206 3.374-2.30c.05-.012.12-.026.166.016s.042.12.037.141c-.03.129-1.227 1.241-1.846 1.817-.193.18-.33.307-.358.336a8 8 0 0 1-.188.186c-.38.366-.664.64.015 1.088.327.216.589.393.85.571.284.194.568.387.936.629q.14.092.27.187c.331.236.63.448.997.414.214-.02.435-.22.547-.82.265-1.417.786-4.486.906-5.751a1.4 1.4 0 0 0-.013-.315.34.34 0 0 0-.114-.217.53.53 0 0 0-.31-.093c-.3.005-.763.166-2.984 1.09"/>
                    </svg>
                    <span class="contact-tooltip">Telegram</span>
                  </a>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    </div>
</template>



<style scoped>
.about {
  min-height: 100vh;
  width: 100vw;
  background-image: url('@/assets/wallpaper.jpeg');
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  background-attachment: fixed;
  overflow-x: hidden;
  position: relative;
}

.about::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.02);
  z-index: 0;
  pointer-events: none;
}

.about-content {
  min-height: 100vh;
  display: grid;
  grid-template-columns: 1fr 1fr;
  padding-top: 80px;
  overflow-x: hidden;
}
.left-section {
  display: flex;
  align-items: center;
  padding: 2rem 3rem;
  background: rgba(255, 255, 255, 0.9);
  backdrop-filter: blur(10px);
  border-right: 1px solid rgba(0, 0, 0, 0.1);
  position: relative;
  z-index: 1;
}
.about-info {
  width: 100%;
  max-width: 500px;
}
.about-title {
  font-size: 3.5rem;
  font-weight: 900;
  margin-bottom: 1.5rem;
  color: #1e293b;
  line-height: 1.1;
}
.gradient-text {
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.about-description {
  font-size: 1.2rem;
  line-height: 1.7;
  color: #475569;
  margin-bottom: 2.5rem;
}
.skills-section,
.services-section {
  margin-bottom: 2rem;
}
.skills-section h3,
.services-section h3 {
  font-size: 1.5rem;
  font-weight: 700;
  color: #1e293b;
  margin-bottom: 1rem;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(2, 1fr);
  gap: 1rem;
  justify-items: center;
  max-width: 300px;
  margin: 0 auto;
}

.keycap {
  position: relative;
  display: inline-block;
  width: 80px;
  height: 80px;
  border-radius: 10px;
  background: linear-gradient(180deg, #282828, #202020);
  box-shadow:
    inset -8px 0 8px rgba(0, 0, 0, 0.15),
    inset 0 -8px 8px rgba(0, 0, 0, 0.25),
    0 0 0 2px rgba(0, 0, 0, 0.75),
    10px 20px 25px rgba(0, 0, 0, 0.4);
  overflow: hidden;
  transition:
    transform 0.1s ease-in-out,
    box-shadow 0.1s ease-in;
  user-select: none;
  -webkit-tap-highlight-color: transparent;
}
.keycap .letter {
  position: absolute;
  left: 12px;
  top: 12px;
  color: #e9e9e9;
  font-size: 12px;
  font-weight: 600;
  transition: transform 0.1s ease-in-out;
  line-height: 1.2;
  max-width: 56px;
  word-wrap: break-word;
}
.keycap::before {
  content: "";
  position: absolute;
  top: 3px;
  left: 4px;
  bottom: 14px;
  right: 12px;
  background: linear-gradient(90deg, #232323, #4a4a4a);
  border-radius: 10px;
  box-shadow:
    -10px -10px 10px rgba(255, 255, 255, 0.25),
    10px 5px 10px rgba(0, 0, 0, 0.15);
  border-left: 1px solid rgba(0, 0, 0, 0.4);
  border-bottom: 1px solid rgba(0, 0, 0, 0.4);
  border-top: 1px solid rgba(0, 0, 0, 0.9);
  transition: all 0.1s ease-in-out;
}

.keycap:active {
  transform: translateY(2px);
  box-shadow:
    inset -4px 0 4px rgba(0, 0, 0, 0.1),
    inset 0 -4px 4px rgba(0, 0, 0, 0.15),
    0 0 0 2px rgba(0, 0, 0, 0.5),
    5px 10px 15px rgba(0, 0, 0, 0.3);
}

.keycap:active::before {
  top: 5px;
  left: 5px;
  bottom: 11px;
  right: 11px;
  box-shadow:
    -5px -5px 5px rgba(255, 255, 255, 0.15),
    5px 3px 5px rgba(0, 0, 0, 0.1);
}

.keycap:active .letter {
  transform: translateY(1px);
}
.pricing-cards {
  display: flex;
  flex-direction: row;
  gap: 1rem;
  justify-content: space-between;
  align-items: stretch;
}
.card {
  width: 200px;
  height: 420px;
  padding: .8em;
  background: #f5f5f5;
  position: relative;
  overflow: visible;
  box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 1px 2px rgba(0,0,0,0.24);
  display: flex;
  flex-direction: column;
}
.card-img {
  height: 60px;
  width: 100%;
  border-radius: .5rem;
  transition: .3s ease;
  flex-shrink: 0;
}
.lite-bg {
  background-color: #00ffa0;
}
.standard-bg {
  background-color: #ffd700;
}

.premium-bg {
  background-color: #ff605c;
}

.card-info {
  padding-top: 12px;
  flex-grow: 1;
  display: flex;
  flex-direction: column;
}
.card-footer {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  padding-top: 10px;
  border-top: 1px solid #ddd;
  margin-top: auto;
  flex-shrink: 0;
}
.text-title {
  font-weight: 900;
  font-size: 1.2em;
  line-height: 1.5;
  margin: 0;
}
.text-body {
  font-size: .9em;
  padding-bottom: 10px;
  margin: 0;
}
.card-img:hover {
  transform: translateY(-25%);
  box-shadow: rgba(226, 196, 63, 0.25) 0px 13px 47px -5px, rgba(180, 71, 71, 0.3) 0px 8px 16px -8px;
}
.check-list {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-top: 0.8rem;
  flex-grow: 1;
}

.check-list-item {
  display: flex;
  align-items: center;
  gap: 6px;
  font-size: 0.9rem;
  line-height: 1.4;
}

.check-list-item span {
  font-weight: bold;
  color: #333;
  flex-shrink: 0;
}
.right-section {
  display: flex;
  flex-direction: column;
  justify-content: center;
  padding: 2rem 3rem;
  background: rgba(0, 0, 0, 0.8);
  backdrop-filter: blur(10px);
  color: white;
  position: relative;
  z-index: 1;
}
.featured-project {
  margin-bottom: 3rem;
}
.featured-project h3,
.contact-section h3 {
  font-size: 1.8rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.project-showcase {
  display: block;
  background: rgba(255, 255, 255, 0.1);
  border-radius: 16px;
  padding: 1.5rem;
  text-decoration: none;
  color: white;
  transition: all 0.3s ease;
  border: 1px solid rgba(255, 255, 255, 0.1);
  backdrop-filter: blur(20px);
}
.project-showcase:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateY(-5px);
  box-shadow: 0 20px 40px rgba(0, 0, 0, 0.3);
}
.browser-header {
  display: flex;
  align-items: center;
  gap: 1rem;
  margin-bottom: 1.5rem;
  padding-bottom: 1rem;
  border-bottom: 1px solid rgba(255, 255, 255, 0.1);
}
.browser-buttons {
  display: flex;
  gap: 8px;
}
.red {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #ff605c;
}
.yellow {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #ffbd44;
}
.green {
  width: 12px;
  height: 12px;
  border-radius: 50%;
  background-color: #00ca4e;
}
.browser-url {
  font-family: 'Courier New', monospace;
  font-size: 0.9rem;
  opacity: 0.7;
}
.project-name {
  font-size: 2rem;
  font-weight: 800;
  margin-bottom: 0.8rem;
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.project-desc {
  font-size: 1rem;
  line-height: 1.6;
  opacity: 0.9;
  margin-bottom: 1rem;
}

.project-tech {
  display: flex;
  gap: 0.5rem;
}

.project-tech span {
  background: rgba(0, 212, 255, 0.2);
  padding: 0.3rem 0.8rem;
  border-radius: 15px;
  font-size: 0.8rem;
  font-weight: 600;
  border: 1px solid rgba(0, 212, 255, 0.3);
}

@media (max-width: 768px) {
  .about {
    background-attachment: scroll;
    background-size: auto 100%;
    background-position: center center;
  }
  
  .about::before {
    background: rgba(0, 0, 0, 0.05);
  }
  
  .about-content {
    grid-template-columns: 1fr;
    grid-template-rows: auto auto;
    padding-top: 140px;
    gap: 0;
  }
  
  .left-section {
    padding: 2.5rem 2rem;
    border-right: none;
    border-bottom: 1px solid rgba(0, 0, 0, 0.1);
    background: rgba(255, 255, 255, 0.85);
  }
  
  .right-section {
    padding: 2.5rem 2rem;
    background: rgba(0, 0, 0, 0.75);
  }
  
  .about-title {
    font-size: 3rem;
    text-align: center;
    margin-bottom: 1.8rem;
  }
  
  .about-description {
    font-size: 1.25rem;
    text-align: center;
    margin-bottom: 2.5rem;
    line-height: 1.8;
  }
  
  .skills-section h3,
  .services-section h3 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 2rem;
  }
  
  .skills-grid {
    gap: 1.2rem;
    max-width: 360px;
    margin: 0 auto 3rem;
  }
  
  .keycap {
    width: 85px;
    height: 85px;
  }
  
  .keycap .letter {
    font-size: 12px;
    left: 10px;
    top: 10px;
    max-width: 65px;
  }
  
  .pricing-cards {
    gap: 1.5rem;
    flex-direction: column;
    align-items: center;
  }
  
  .card {
    width: min(80vw, 360px);
    height: 400px;
    padding: 1.2rem;
  }
  
  .text-title {
    font-size: 1.4em;
  }
  
  .text-body {
    font-size: 1.1em;
  }
  
  .check-list-item {
    font-size: 1rem;
  }
  
  .featured-project h3 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 2rem;
  }
  
  .contact-section h3 {
    text-align: center;
    font-size: 2rem;
    margin-bottom: 2rem;
  }
  
  .project-showcase {
    padding: 2rem;
    margin-bottom: 2.5rem;
  }
  
  .project-name {
    font-size: 2rem;
  }
  
  .project-desc {
    font-size: 1.2rem;
  }
  
  .team-contacts {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .developer-card {
    padding: 1.8rem;
  }
  
  .dev-avatar {
    width: 70px;
    height: 70px;
  }
  
  .dev-icon {
    width: 32px;
    height: 32px;
  }
  
  .dev-name {
    font-size: 1.2rem;
  }
  
  .dev-subtitle {
    font-size: 0.8rem;
  }
  
  .contact-item a {
    width: 50px;
    height: 50px;
  }
  
  .contact-item a svg {
    width: 22px;
    height: 22px;
  }
}

@media (max-width: 600px) {
  .about {
    background-size: cover;
    background-position: center top;
  }
  
  .about::before {
    background: rgba(0, 0, 0, 0.08);
  }
  
  .about-content {
    padding-top: 150px;
  }
  
  .left-section {
    padding: 2rem 1.5rem;
    background: rgba(255, 255, 255, 0.8);
  }
  
  .right-section {
    padding: 2rem 1.5rem;
    background: rgba(0, 0, 0, 0.7);
  }
  
  .about-title {
    font-size: 2.6rem;
    margin-bottom: 1.5rem;
  }
  
  .about-description {
    font-size: 1.15rem;
    margin-bottom: 2rem;
    padding: 0 0.5rem;
  }
  
  .skills-section h3,
  .services-section h3 {
    font-size: 1.8rem;
    margin-bottom: 1.5rem;
  }
  
  .skills-grid {
    gap: 1rem;
    max-width: 320px;
    margin-bottom: 2.5rem;
  }
  
  .keycap {
    width: 80px;
    height: 80px;
  }
  
  .keycap .letter {
    font-size: 11px;
    left: 8px;
    top: 8px;
    max-width: 64px;
  }
  
  .pricing-cards {
    gap: 1.2rem;
  }
  
  .card {
    width: min(85vw, 330px);
    height: 380px;
    padding: 1rem;
  }
  
  .text-title {
    font-size: 1.3em;
  }
  
  .text-body {
    font-size: 1em;
  }
  
  .check-list-item {
    font-size: 0.95rem;
  }
  
  .featured-project h3 {
    font-size: 1.8rem;
    margin-bottom: 1.5rem;
  }
  
  .contact-section h3 {
    text-align: center;
    font-size: 1.8rem;
    margin-bottom: 1.5rem;
  }
  
  .project-showcase {
    padding: 1.5rem;
    margin-bottom: 2rem;
  }
  
  .project-name {
    font-size: 1.8rem;
  }
  
  .project-desc {
    font-size: 1.1rem;
  }
  
  .team-contacts {
    gap: 1.2rem;
  }
  
  .developer-card {
    padding: 1.5rem;
  }
  
  .dev-avatar {
    width: 65px;
    height: 65px;
  }
  
  .dev-icon {
    width: 28px;
    height: 28px;
  }
  
  .dev-name {
    font-size: 1.1rem;
  }
  
  .dev-subtitle {
    font-size: 0.75rem;
  }
  
  .contact-item a {
    width: 46px;
    height: 46px;
  }
  
  .contact-item a svg {
    width: 20px;
    height: 20px;
  }
}

@media (max-width: 480px) {
  .about {
    background-size: auto 120%;
    background-position: center 20%;
  }
  
  .about::before {
    background: rgba(0, 0, 0, 0.1);
  }
  
  .about-content {
    padding-top: 110px;
  }
  
  .left-section {
    padding: 1.5rem 1rem;
    background: rgba(255, 255, 255, 0.75);
  }
  
  .right-section {
    padding: 1.5rem 1rem;
    background: rgba(0, 0, 0, 0.65);
  }
  
  .about-title {
    font-size: 2.2rem;
    margin-bottom: 1.2rem;
  }
  
  .about-description {
    font-size: 1rem;
    margin-bottom: 1.8rem;
    padding: 0 0.5rem;
  }
  
  .skills-section h3,
  .services-section h3 {
    font-size: 1.5rem;
    margin-bottom: 1.2rem;
  }
  
  .skills-grid {
    gap: 0.8rem;
    max-width: 280px;
    margin-bottom: 2rem;
  }
  
  .keycap {
    width: 75px;
    height: 75px;
  }
  
  .keycap .letter {
    font-size: 10px;
    left: 6px;
    top: 6px;
    max-width: 63px;
  }
  
  .pricing-cards {
    gap: 1.5rem;
  }
  
  .card {
    width: min(90vw, 310px);
    height: 370px;
    padding: 1rem;
    font-size: 0.95rem;
  }
  
  .text-title {
    font-size: 1.2em;
  }
  
  .text-body {
    font-size: 0.9em;
  }
  
  .check-list-item {
    font-size: 0.85rem;
    gap: 4px;
    line-height: 1.5;
  }
  
  .featured-project h3 {
    font-size: 1.5rem;
    margin-bottom: 1.2rem;
  }
  
  .contact-section h3 {
    text-align: center;
    font-size: 1.5rem;
    margin-bottom: 1.2rem;
  }
  
  .project-showcase {
    padding: 1.2rem;
    margin-bottom: 1.5rem;
  }
  
  .project-name {
    font-size: 1.6rem;
  }
  
  .project-desc {
    font-size: 1rem;
  }
  
  .browser-url {
    font-size: 0.8rem;
  }
  
  .project-tech span {
    font-size: 0.75rem;
    padding: 0.25rem 0.6rem;
  }
  
  .team-contacts {
    gap: 1rem;
  }
  
  .developer-card {
    padding: 1.2rem;
  }
  
  .dev-avatar {
    width: 60px;
    height: 60px;
    margin-bottom: 0.8rem;
  }
  
  .dev-icon {
    width: 26px;
    height: 26px;
  }
  
  .dev-name {
    font-size: 1rem;
  }
  
  .dev-subtitle {
    font-size: 0.7rem;
  }
  
  .dev-role {
    font-size: 0.8rem;
  }
  
  .contact-item a {
    width: 42px;
    height: 42px;
  }
  
  .contact-item a svg {
    width: 18px;
    height: 18px;
  }
  
  .contact-tooltip {
    font-size: 11px;
    padding: 3px 6px;
  }
}

@media (max-width: 360px) {
  .about {
    background-size: auto 140%;
    background-position: center 30%;
  }
  
  .about::before {
    background: rgba(0, 0, 0, 0.12);
  }
  
  .about-content {
    padding-top: 120px;
  }
  
  .left-section {
    padding: 1.2rem 0.8rem;
    background: rgba(255, 255, 255, 0.7);
  }
  
  .right-section {
    padding: 1.2rem 0.8rem;
    background: rgba(0, 0, 0, 0.6);
  }
  
  .about-title {
    font-size: 1.9rem;
    margin-bottom: 1rem;
  }
  
  .about-description {
    font-size: 0.95rem;
    margin-bottom: 1.5rem;
    padding: 0 0.3rem;
  }
  
  .skills-section h3,
  .services-section h3 {
    font-size: 1.3rem;
    margin-bottom: 1rem;
  }
  
  .skills-grid {
    max-width: 250px;
    gap: 0.6rem;
    margin-bottom: 1.8rem;
  }
  
  .keycap {
    width: 68px;
    height: 68px;
  }
  
  .keycap .letter {
    font-size: 9px;
    left: 5px;
    top: 5px;
    max-width: 58px;
  }
  
  .card {
    width: min(95vw, 290px);
    height: 350px;
    padding: 0.8rem;
  }
  
  .text-title {
    font-size: 1.1em;
  }
  
  .text-body {
    font-size: 0.85em;
  }
  
  .check-list-item {
    font-size: 0.75rem;
    gap: 3px;
  }
  
  .featured-project h3 {
    font-size: 1.3rem;
    margin-bottom: 1rem;
  }
  
  .contact-section h3 {
    text-align: center;
    font-size: 1.3rem;
    margin-bottom: 1rem;
  }
  
  .project-showcase {
    padding: 1rem;
    margin-bottom: 1.2rem;
  }
  
  .project-name {
    font-size: 1.4rem;
  }
  
  .project-desc {
    font-size: 0.9rem;
  }
  
  .browser-url {
    font-size: 0.75rem;
  }
  
  .project-tech span {
    font-size: 0.7rem;
    padding: 0.2rem 0.5rem;
  }
  
  .team-contacts {
    gap: 0.8rem;
  }
  
  .developer-card {
    padding: 1rem;
  }
  
  .dev-info {
    margin-bottom: 1rem;
  }
  
  .dev-avatar {
    width: 55px;
    height: 55px;
    margin-bottom: 0.6rem;
  }
  
  .dev-icon {
    width: 24px;
    height: 24px;
  }
  
  .dev-name {
    font-size: 0.9rem;
    margin-bottom: 0.3rem;
  }
  
  .dev-subtitle {
    font-size: 0.65rem;
  }
  
  .dev-role {
    font-size: 0.75rem;
  }
  
  .dev-contacts {
    gap: 0.8rem;
  }
  
  .contact-item a {
    width: 38px;
    height: 38px;
  }
  
  .contact-item a svg {
    width: 16px;
    height: 16px;
  }
  
  .contact-tooltip {
    font-size: 10px;
    padding: 2px 5px;
  }
}

.contact-section h3 {
  font-size: 1.8rem;
  font-weight: 700;
  margin-bottom: 1.5rem;
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}

.team-contacts {
  display: grid;
  grid-template-columns: 1fr 1fr;
  gap: 2rem;
  margin-top: 2rem;
}

.developer-card {
  background: rgba(255, 255, 255, 0.1);
  border-radius: 20px;
  padding: 2rem;
  backdrop-filter: blur(15px);
  border: 1px solid rgba(255, 255, 255, 0.2);
  transition: all 0.3s ease;
  text-align: center;
}

.developer-card:hover {
  background: rgba(255, 255, 255, 0.15);
  transform: translateY(-5px);
  box-shadow: 0 15px 35px rgba(0, 0, 0, 0.2);
  border-color: rgba(255, 255, 255, 0.3);
}

.dev-info {
  margin-bottom: 1.5rem;
}

.dev-avatar {
  width: 80px;
  height: 80px;
  border-radius: 50%;
  background: linear-gradient(135deg, #00d4ff 0%, #0099cc 100%);
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 auto 1rem;
  box-shadow: 0 8px 20px rgba(0, 212, 255, 0.3);
  transition: all 0.3s ease;
}

.developer-card:hover .dev-avatar {
  transform: scale(1.1);
  box-shadow: 0 12px 30px rgba(0, 212, 255, 0.4);
}

.dev-icon {
  width: 36px;
  height: 36px;
  filter: brightness(0) invert(1);
  transition: all 0.3s ease;
}

.dev-name {
  font-size: 1.3rem;
  font-weight: 700;
  margin-bottom: 0.5rem;
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  line-height: 1.2;
}

.dev-subtitle {
  font-size: 0.9rem;
  font-weight: 500;
  opacity: 0.9;
  background: linear-gradient(45deg, #ff605c, #ffbd44, #00ca4e);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
  display: block;
}

.dev-role {
  font-size: 0.9rem;
  opacity: 0.8;
  margin: 0;
  color: rgba(255, 255, 255, 0.9);
}

.dev-contacts {
  display: flex;
  justify-content: center;
  gap: 1rem;
  flex-wrap: wrap;
}

.contact-item {
  position: relative;
}

.contact-item a {
  position: relative;
  overflow: hidden;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 45px;
  height: 45px;
  border-radius: 50%;
  color: #4d4d4d;
  background-color: #fff;
  transition: all 0.3s ease-in-out;
  text-decoration: none;
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

.contact-item a:hover {
  color: white;
  transform: translateY(-3px);
  box-shadow: 0 8px 25px rgba(0, 0, 0, 0.2);
}

.contact-item a svg {
  position: relative;
  z-index: 1;
  width: 20px;
  height: 20px;
}

.contact-filled {
  position: absolute;
  top: auto;
  bottom: 0;
  left: 0;
  width: 100%;
  height: 0;
  background-color: #000;
  transition: all 0.3s ease-in-out;
  border-radius: 50%;
}

.contact-item a:hover .contact-filled {
  height: 100%;
}

.contact-item a[data-social="linkedin"] .contact-filled {
  background-color: #0274b3;
}

.contact-item a[data-social="github"] .contact-filled {
  background-color: #24262a;
}

.contact-item a[data-social="email"] .contact-filled {
  background-color: #ea4335;
}

.contact-item a[data-social="telegram"] .contact-filled {
  background-color: #0088cc;
}

.contact-tooltip {
  position: absolute;
  top: -35px;
  left: 50%;
  transform: translateX(-50%);
  color: #fff;
  padding: 4px 8px;
  border-radius: 6px;
  background-color: rgba(0, 0, 0, 0.8);
  opacity: 0;
  visibility: hidden;
  font-size: 12px;
  transition: all 0.3s ease;
  white-space: nowrap;
  pointer-events: none;
}

.contact-item:hover .contact-tooltip {
  opacity: 1;
  visibility: visible;
  top: -45px;
}
</style>
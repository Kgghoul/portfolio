# ⚡ Быстрый деплой на GitHub Pages

## 1. Обновите название репозитория в vite.config.js

```js
base: process.env.NODE_ENV === 'production' ? '/ваше-название-репозитория/' : '/',
```

## 2. Команды для деплоя

```bash
# Загрузка в репозиторий
git add .
git commit -m "Deploy portfolio website"
git remote add origin https://github.com/username/repository-name.git
git push -u origin main

# Или если репозиторий уже подключен:
git add .
git commit -m "Update portfolio"
git push
```

## 3. Настройка GitHub Pages

1. GitHub репозиторий → **Settings** → **Pages**
2. Source: **GitHub Actions**
3. Готово! 🚀

## 📍 Ваш сайт: `https://username.github.io/repository-name/`

---

**Автоматический деплой**: каждый push → автоматическая сборка и обновление сайта!

# ✅ Чек-лист готовности к деплою

## Перед деплоем проверьте:

### 🔧 Конфигурация

- [ ] **vite.config.js**: base path настроен правильно
  ```js
  base: process.env.NODE_ENV === 'production' ? '/your-repo-name/' : '/',
  ```
- [ ] **package.json**: скрипт `build` присутствует
- [ ] **.gitignore**: папка `dist/` исключена

### 📁 Файлы GitHub Actions

- [ ] **`.github/workflows/deploy.yml`** создан
- [ ] **Workflow file** содержит правильные настройки Node.js

### 🖼️ Ресурсы

- [ ] **Изображения** находятся в `src/assets/`
- [ ] **Пути к изображениям** используют `@/assets/`
- [ ] **Публичные файлы** в папке `public/`

### 🌐 Маршрутизация

- [ ] **Router** использует `import.meta.env.BASE_URL`
- [ ] **Все ссылки** используют `RouterLink` или правильные пути

### 🎨 Контент

- [ ] **Переводы** работают корректно (RU/EN)
- [ ] **Контакты** содержат реальные ссылки
- [ ] **Проектные ссылки** активны и работают

### 🔗 GitHub Repository

- [ ] **Репозиторий создан** на GitHub
- [ ] **Название репозитория** соответствует base path
- [ ] **README.md** или **DEPLOY.md** добавлен

## 🚀 Команды для деплоя:

```bash
# Финальная проверка
npm run build

# Коммит и пуш
git add .
git commit -m "Ready for deployment"
git push origin main
```

## 🌐 После деплоя:

1. **GitHub** → **Settings** → **Pages** → **GitHub Actions**
2. **Ждите завершения** GitHub Actions (2-3 минуты)
3. **Проверьте сайт** по адресу: `https://username.github.io/repository/`

---

### 🆘 Если что-то не работает:

- Проверьте **Actions** tab в GitHub репозитории
- Убедитесь что **base path** в `vite.config.js` правильный
- Проверьте что **GitHub Pages** настроен на **GitHub Actions**

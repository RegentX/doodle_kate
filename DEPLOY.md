# Выложить игру на GitHub Pages

Для этого репозитория сайт уже опубликован:
https://regentx.github.io/doodle_kate/

Ниже — как это устроено и как обновлять.

Игра — один статический файл `index.html`: сборка, сервер и база данных не нужны.
GitHub Pages отдаёт его как обычный сайт.

## Вариант 1 — через сайт GitHub (проще)

1. Создай **публичный** репозиторий, например `katya-jump`.
2. Загрузи в **корень** репозитория:
   - `index.html` — обязательно;
   - `README.md`, `DEPLOY.md` — по желанию.
   Важно: `index.html` должен лежать в корне, а не внутри папки `katya-jump`.
3. Открой **Settings → Pages**.
4. В блоке **Build and deployment**:
   - **Source:** `Deploy from a branch`;
   - **Branch:** `main`, папка `/ (root)`;
   - нажми **Save**.
5. Подожди 1–2 минуты. Адрес будет такой:

   `https://USERNAME.github.io/katya-jump/`

   где `USERNAME` — твой логин GitHub.

Если загрузить папку `katya-jump` целиком, адрес станет
`https://USERNAME.github.io/katya-jump/katya-jump/` — лучше загружать
содержимое папки, а не саму папку.

## Вариант 2 — через git в терминале

```bash
cd katya-jump
git init
git add index.html README.md DEPLOY.md
git commit -m "Прыжки Кати"
git branch -M main
git remote add origin https://github.com/USERNAME/katya-jump.git
git push -u origin main
```

Дальше включи Pages в **Settings → Pages** как в варианте 1.

## Обновления

Изменил `index.html` → сделай commit и push. Pages пересоберёт сайт
автоматически за 1–2 минуты.

## Если открывается 404

- `index.html` точно в корне репозитория?
- В Pages выбрана ветка `main` и папка `/ (root)`?
- Прошло хотя бы 2 минуты?
- Проверь вкладку **Actions** / настройки Pages на ошибки.

## Приватность и localStorage

- Публичный репозиторий = публичная страница. Имена Кати и Саши,
  текст признания и пиксельные арты будут видны всем, у кого есть ссылка.
- Настоящих фотографий в игре нет — только пиксельные спрайты.
- Приватный репозиторий с Pages обычно требует GitHub Pro/Team.
- Рекорды и выбранный скин хранятся в `localStorage` **у каждого посетителя**
  в его браузере. На новом адресе они начнутся заново.

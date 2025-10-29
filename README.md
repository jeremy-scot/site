# raw-like-netlify

Статический набор файлов, готовый для деплоя на **Netlify**.  
Файлы будут доступны по пути `/raw/...` и отдаваться с заголовком `Content-Type: text/plain; charset=utf-8`.

## Структура
```
/public
  /raw
    /examples/example.lua
  viewer.html
_headers
netlify.toml
```

## Как использовать
1. Распакуйте в корень репозитория или директорию с кодом.
2. Закоммитьте и запушьте в GitHub.
3. Подключите репозиторий в Netlify: в поле *Publish directory* укажите `public`.
4. Либо локально:
   - Установите netlify-cli: `npm i -g netlify-cli`
   - Войдите: `netlify login`
   - Разверните: `netlify deploy --dir=public --prod`

После деплоя файл `example.lua` будет доступен по:
`https://<your-site>.netlify.app/raw/examples/example.lua`

## Примечания
- По умолчанию Netlify назначает `Content-Type` по расширению, но файл `_headers` принудительно устанавливает `text/plain` для всех URL, начинающихся с `/raw/`.
- Не размещайте секреты или приватные ключи в папке `public`.

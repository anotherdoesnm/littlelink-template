# littlelink-template

Шаблон страницы-визитки: в репозитории только конфиги, сборку делает
[`anotherdoesnm/action-littlelink`](https://github.com/anotherdoesnm/action-littlelink).

## Быстрый старт

1. **Use this template** → создайте свой репозиторий.
2. В `site.json` — имя, подпись, подвал. В `links.json` — ссылки.
3. Положите `assets/avatar.png` (квадратную картинку).
4. Settings → Pages → Source: **GitHub Actions**.
5. Пуш в `main` — через минуту страница на `https://<user>.github.io/<repo>/`.

## Как добавить свою иконку

```
assets/icons/myservice.svg     ← любой SVG, viewBox желателен 0 0 24 24
```

```json
{ "label": "Мой сервис", "url": "https://example.org",
  "brand": "myservice", "icon": "myservice", "color": "#123456" }
```

`icon` — имя файла без `.svg`. Если для `brand` нет правила в апстримных
`brands.css` и нет своего в `local.css` действия, сборщик возьмёт `color` из
конфига и сам подберёт цвет текста по контрасту. Ровно так в примере выше сделан
«Мой сервис».

Признак того, что иконка не подхватилась: в логе сборки `icon "…" missing — using a
letter badge`, а в HTML вместо картинки буква в кружке.

## Что можно трогать, а что нет

| файл | можно |
|---|---|
| `site.json`, `links.json` | да, это и есть содержимое |
| `assets/icons/*.svg`, `assets/avatar.png` | да |
| `.github/workflows/build.yml` | обычно не нужно |
| вёрстка и цвета кнопок | живут в action-репозитории, не здесь |

# Задание 2 - Проектирование API (экран выбора магазина)

По макету есть экран "Выберите магазин" со списком партнеров. Для каждого партнера нужно:
- название,
- текст про ближайшую доставку или про быструю доставку,
- логотип,
- ссылка, по которой при нажатии на карточку выполняется переход на внешний ресурс.

## 1) Пример REST API запроса

get /api/v1/partners

Пример запроса:
- URL:
  - get /api/v1/partners?city_id=spb&locale=ru_RU
- Заголовки:
  - authorization: bearer <access_token>
  - x-client-platform: ios (или android)
  - x-app-version: 1.12.0

## 2) Пример ответа (JSON)

```json
{
  "screen_title": "Выберите магазин",
  "partners": [
    {
      "id": "metro",
      "name": "METRO",
      "delivery": {
        "type": "time_slot",
        "label": "Ближайшая доставка",
        "day": "сегодня",
        "from": "21:00",
        "to": "23:00"
      },
      "logo_url": "https://cdn.petrushka.example/partners/metro/logo.png",
      "external_url": "https://metro.example/landing?p=petrushka"
    },
    {
      "id": "auchan",
      "name": "Ашан",
      "delivery": {
        "type": "time_slot",
        "label": "Ближайшая доставка",
        "day": "сегодня",
        "from": "18:00",
        "to": "20:00"
      },
      "logo_url": "https://cdn.petrushka.example/partners/auchan/logo.png",
      "external_url": "https://auchan.example/landing?p=petrushka"
    },
    {
      "id": "vkusvill",
      "name": "ВкусВилл",
      "delivery": {
        "type": "fast_delivery",
        "label": "Быстрая доставка",
        "min_minutes": 20,
        "max_minutes": 60
      },
      "logo_url": "https://cdn.petrushka.example/partners/vkusvill/logo.png",
      "external_url": "https://vkusvill.example/landing?p=petrushka"
    },
    {
      "id": "victoria",
      "name": "ВИКТОРИЯ",
      "delivery": {
        "type": "time_slot",
        "label": "Ближайшая доставка",
        "day": "сегодня",
        "from": "17:00",
        "to": "19:00"
      },
      "logo_url": "https://cdn.petrushka.example/partners/victoria/logo.png",
      "external_url": "https://victoria.example/landing?p=petrushka"
    }
  ]
}

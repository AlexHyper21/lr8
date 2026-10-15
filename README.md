# ЛР 8 — REST API на Express.js и MongoDB

Бэкенд интернет-магазина цифровых товаров «пиксельмаркет» (вариант 3). CRUD-операции для сущности **Product**.

## Стек

Node.js, Express 4, MongoDB, Mongoose 8, dotenv, nodemon.

## Подготовка MongoDB

Вариант 1 — локально: установите MongoDB Community Server (https://www.mongodb.com/try/download/community), служба запустится на `mongodb://127.0.0.1:27017`.

Вариант 2 — MongoDB Atlas: создайте бесплатный кластер, скопируйте строку подключения и укажите её в `.env`.

## Настройка

Файл `.env` (образец — `.env.example`):

```
PORT=5000
MONGODB_URI=mongodb://127.0.0.1:27017/pixelmarket
```

## Запуск

```bash
npm install
npm run dev
```

или без автоперезапуска:

```bash
npm start
```

Сервер: http://localhost:5000

## Эндпоинты

| Метод | URL | Назначение | Код ответа |
|---|---|---|---|
| GET | /api/products | список всех товаров | 200 |
| GET | /api/products/:id | товар по id | 200, 400, 404 |
| POST | /api/products | создание товара | 201, 400 |
| PUT | /api/products/:id | обновление товара | 200, 400, 404 |
| DELETE | /api/products/:id | удаление товара | 200, 400, 404 |

Пример тела запроса POST:

```json
{
  "name": "Набор иконок «Контур» · 640 штук",
  "price": 29,
  "imageUrl": "/images/product-1.webp"
}
```

## Postman

Импортируйте `lr8.postman_collection.json` (Postman → Import). Запрос «Создать товар» сохраняет `_id` в переменную `productId`, остальные запросы используют её автоматически. Запускайте запросы по порядку.

```markdown

Простое REST API для управления продуктами, разработанное на Spring Boot с использованием PostgreSQL.

✨ Функционал
- Полный CRUD для продуктов
- Валидация данных
- Документация API через Swagger UI
- Подключение к PostgreSQL
- Готовая конфигурация для деплоя

🛠️ Технологии
Backend: 
  - Java 21
  - Spring Boot 3.2.0
  - Spring Data JPA
  - HikariCP
- База данных: PostgreSQL 14+
- Документация: Springdoc OpenAPI 2.3.0

🚀 Установка

1. Клонировать репозиторий:
   ```bash
   git clone https://github.com/yourusername/product-api.git
   cd product-api
   ```

2. Настроить базу данных:
   ```sql
   CREATE DATABASE products;
   CREATE USER api_user WITH PASSWORD 'secure_password';
   GRANT ALL PRIVILEGES ON DATABASE products TO api_user;
   ```
3. Запустить приложение:
   ```bash
   mvn spring-boot:run
   ```

🔌 API Endpoints

Основные endpoints:
| Метод | Endpoint               | Описание                |
|-------|------------------------|-------------------------|
| GET   | `/api/products`        | Получить все продукты   |
| GET   | `/api/products/{id}`   | Получить продукт по ID  |
| POST  | `/api/products`        | Создать новый продукт   |
| PUT   | `/api/products/{id}`   | Обновить продукт        |
| DELETE| `/api/products/{id}`   | Удалить продукт         |

Пример запроса (POST /api/products):
```json
{
  "name": "Example Product",
  "price": 19.99
}
```
---

```markdown
# Product Management REST API

![Java](https://img.shields.io/badge/Java-21-blue)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2.0-green)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14-blue)

Простое REST API для управления продуктами, разработанное на Spring Boot с использованием PostgreSQL.

## 📋 Оглавление
- [Функционал](#✨-функционал)
- [Технологии](#🛠️-технологии)
- [Установка](#🚀-установка)
- [Использование](#💻-использование)
- [API Endpoints](#🔌-api-endpoints)
- [Развертывание](#☁️-развертывание)
- [Лицензия](#📜-лицензия)

## ✨ Функционал
- Полный CRUD для продуктов
- Валидация данных
- Документация API через Swagger UI
- Подключение к PostgreSQL
- Готовая конфигурация для деплоя

## 🛠️ Технологии
- **Backend**: 
  - Java 21
  - Spring Boot 3.2.0
  - Spring Data JPA
  - HikariCP
- **База данных**: PostgreSQL 14+
- **Документация**: Springdoc OpenAPI 2.3.0

## 🚀 Установка

1. **Клонировать репозиторий**:
   ```bash
   git clone https://github.com/yourusername/product-api.git
   cd product-api
   ```

2. **Настроить базу данных**:
   ```sql
   CREATE DATABASE products;
   CREATE USER api_user WITH PASSWORD 'secure_password';
   GRANT ALL PRIVILEGES ON DATABASE products TO api_user;
   ```

3. **Настроить приложение**:
   Скопируйте `application.properties.example` в `application.properties` и укажите свои настройки.

4. **Запустить приложение**:
   ```bash
   mvn spring-boot:run
   ```

## 💻 Использование
После запуска приложение будет доступно по адресу: `http://localhost:8080`

### Доступные профили:
- `dev` - для разработки с H2 базой данных
- `prod` - для продакшена с PostgreSQL

Активировать профиль:
```bash
mvn spring-boot:run -Dspring-boot.run.profiles=dev
```

## 🔌 API Endpoints

### Основные endpoints:
| Метод | Endpoint               | Описание                |
|-------|------------------------|-------------------------|
| GET   | `/api/products`        | Получить все продукты   |
| GET   | `/api/products/{id}`   | Получить продукт по ID  |
| POST  | `/api/products`        | Создать новый продукт   |
| PUT   | `/api/products/{id}`   | Обновить продукт        |
| DELETE| `/api/products/{id}`   | Удалить продукт         |

### Пример запроса (POST /api/products):
```json
{
  "name": "Example Product",
  "price": 19.99
}
```

## ☁️ Развертывание

### 1. Как JAR-файл:
```bash
mvn clean package
java -jar target/product-api-0.0.1-SNAPSHOT.jar
```

### 2. В Docker:
```bash
docker build -t product-api .
docker run -p 8080:8080 product-api
```

### 3. На сервере:
1. Скопируйте JAR-файл на сервер
2. Создайте systemd сервис:
   ```bash
   sudo nano /etc/systemd/system/product-api.service
   ```
3. Пример конфигурации сервиса:
   ```ini
   [Unit]
   Description=Product API Service
   After=syslog.target

   [Service]
   User=api-user
   ExecStart=/usr/bin/java -jar /path/to/product-api.jar
   SuccessExitStatus=143

   [Install]
   WantedBy=multi-user.target
   ```
---

<div align="center">
  <sub>Создано с ❤️ для эффективного управления продуктами</sub>
</div>
```

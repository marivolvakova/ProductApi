простое RESTful API приложение, разработанное на Spring Boot, которое предоставляет функционал для управления списком продуктов. Приложение включает полный набор CRUD операций и использует PostgreSQL в качестве базы данных. 
Технологический стек
Backend: Java 21, Spring Boot 3.2.0

База данных: PostgreSQL

Библиотеки:

Spring Web (REST API)

Spring Data JPA (работа с БД)

HikariCP (пул соединений)

Lombok (сокращение boilerplate кода)

Springdoc OpenAPI (документация API)

Функциональность API
Основные эндпоинты:
GET /api/products - получить список всех продуктов

GET /api/products/{id} - получить продукт по ID

POST /api/products - создать новый продукт

PUT /api/products/{id} - обновить существующий продукт

DELETE /api/products/{id} - удалить продукт

Модель данных (Product):
json
{
  "id": 1,
  "name": "Example Product",
  "price": 19.99
}
Установка и запуск
Требования:

Java 21+

PostgreSQL 14+

Maven 3.8+

Настройка базы данных:

Создать БД: CREATE DATABASE products;

Создать пользователя: CREATE USER admin WITH PASSWORD 'password123';

Назначить права: GRANT ALL PRIVILEGES ON DATABASE products TO admin;

Запуск приложения:

bash
mvn spring-boot:run

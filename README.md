# Лабораторна робота №01 — Task Management API

Backend-застосунок для керування проєктами та завданнями, створений на Node.js, Express.js, PostgreSQL та Prisma ORM.

## Реалізовано

- Express.js сервер;
- PostgreSQL + Prisma ORM;
- 5 пов'язаних сутностей: User, Project, ProjectMember, Task, Comment;
- зв'язок 1:N: Project → Task, User → Task, Task → Comment;
- зв'язок M:N: User ↔ Project через ProjectMember;
- ролі USER / MANAGER / ADMIN;
- CRUD для користувачів, проєктів і завдань;
- створення та перегляд коментарів;
- Zod-валідація;
- централізована обробка помилок;
- змінні середовища через `.env`;
- базова API-документація;
- Helmet, CORS, rate limiting, Morgan.

## Встановлення

1. Встановити Node.js LTS та PostgreSQL.
2. Створити БД `task_management`.
3. Скопіювати `.env.example` у `.env`.
4. Вказати правильний `DATABASE_URL`.
5. Виконати:

```bash
npm install
npx prisma generate
npx prisma migrate dev --name init
npm run dev
```

API буде доступний за адресою `http://localhost:3000`.

## Приклад .env

```env
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/task_management?schema=public"
PORT=3000
NODE_ENV=development
```

## Перевірка

```bash
curl http://localhost:3000/api/health
curl http://localhost:3000/api/users
curl http://localhost:3000/api/projects
curl http://localhost:3000/api/tasks
```

Для POST/PUT запитів використовуйте JSON та заголовок `Content-Type: application/json`.

## Структура

```text
src/
├── controllers/
├── middleware/
├── routes/
├── app.js
├── config.js
├── db.js
└── schemas.js
prisma/
└── schema.prisma
reports/
└── lab1-report.md
docs/
└── api.md
```

# Приклад конфігурації

Файл `.env` не додається до GitHub, оскільки може містити пароль до PostgreSQL.

```env
DATABASE_URL="postgresql://postgres:postgres@localhost:5432/task_management?schema=public"
PORT=3000
NODE_ENV=development
```

Перед запуском необхідно створити базу даних `task_management`.

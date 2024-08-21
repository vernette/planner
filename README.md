**Planner** - это веб-приложение для создания, управления и отслеживания задач с возможностью добавлять название,
описание и статус задаче.

- [Запуск проекта](#запуск-проекта)
- [Возможности проекта](#возможности-проекта)
- [Примеры запросов к API](#примеры-запросов-к-api)
- [Используемые технологии](#используемые-технологии)

## Запуск проекта

Клонируйте репозиторий и перейдите в папку с проектом:

```bash
git clone https://github.com/vernette/planner
cd planner
```

### Вручную

Создайте виртуальное окружение и активируйте его:

```bash
python -m venv .venv
source .venv/bin/activate
```

Установите зависимости:

```bash
pip install -r backend/requirements.txt
```

Создайте файл `.env` в корне проекта и внесите свои данные. Для примера можно воспользоваться файлом `.env.example`:

```plaintext
POSTGRES_USER=django_user
POSTGRES_PASSWORD=mysecretpassword
POSTGRES_DB=django
DB_HOST=db
DB_PORT=5432
```

Выполните миграции:

```bash
python backend/manage.py migrate
```

Запустите проект:

```bash
python backend/manage.py runserver
```

### Docker

Запустите оркестр:

```bash
sudo docker compose up
```

## Возможности проекта

Создание, редактирование и удаление задач.
Задаче можно присвоить название и описание, а также статус (**Complete** и **Incomplete**).

## Примеры запросов к API

### Получение списка задач

```http
GET /api/tasks/
```

### Создание задачи

```http
POST /api/tasks/
Content-Type: application/json

{
  "title": "Task 1",
  "description": "Task 1 description",
  "completed": false
}
```

## Используемые технологии

| Тип        | Название   |
| ---------- | ---------- |
| Веб-сервер | Nginx      |
| Бэкенд     | Django     |
| Фронтенд   | React      |
| БД         | PostgreSQL |

## Автор

- [Никита Скрябин](https://github.com/vernette)

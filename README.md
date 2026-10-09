# Course Services

## О проекте
Микросервисная платформа для автоматизации проверки лабораторных работ.

### Сервисы системы
* **bff** — Backend For Frontend, точка входа для клиентских интерфейсов.
* **code-coordinator** — сервис оркестрации и выполнения студенческого кода.
* **course-service** — сервис управления данными курсов, модулями и задачами.
* **plagiarism-service** — сервис анализа решений на заимствования.

---

## Локальный запуск (course-service)

1. Установите менеджер пакетов `uv`:
   ```bash
   pip install uv==0.5.17
   cd course-service
   uv sync --all-groups
   uv run uvicorn src.main:app --host 127.0.0.1 --port 8888 --env-file ".env" --workers 1 --log-level info --no-access-log --log-config log-config.yaml

Документация Swagger доступна по адресу: http://127.0.0.1:8888/docs

## Запуск тестов
   ```bash
   uv run pytest
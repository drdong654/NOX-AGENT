# NOX

Локальный терминал рыночной аналитики. Сейчас реализован первый новостной срез:
загрузка RSS/Atom, нормализация, дедупликация и хранение в SQLite.

## Запуск

Установка в виртуальное окружение:

```bash
python -m venv .venv
.venv/bin/pip install -e .
```

Загрузка одного или нескольких фидов:

```bash
nox news fetch https://example.com/feed.xml --db nox.db
```

Просмотр сохранённых новостей:

```bash
nox news list --db nox.db --limit 20
```

Тесты не требуют сети:

```bash
PYTHONPATH=src python -m unittest discover -s tests -v
```

NOX сохраняет заголовок, ссылку, источник, время публикации и время сбора.
Полные тексты статей не копируются.

# README — Expense Tracker

## Мета репозиторію
Репозиторій містить готові файли для лабораторної: технічне завдання, політику версіонування, шаблони релізів, журнал змін і чекліст приймання.

## Структура репозиторію
```
/lab-Danya-expense-tracker/
├─ TЗ.md
├─ VERSIONING.md
├─ RELEASE_TEMPLATE.md
├─ CHANGELOG.md
├─ ACCEPTANCE_CHECKLIST.md
├─ README.md
├─ design/  # мокапи (опціонально)
```

## Вибір моделі життєвого циклу — Agile (Scrum)
Ми обрали **Agile / Scrum**: 1-тижневі спринти, щоденні стендапи (15 хв), planning, review та retrospective. Це підходить для студентського проєкту: швидкі ітерації, часті демо і можливість адаптуватись.

**Артефакти:** product backlog, sprint backlog, Definition of Done (DoD), release notes.

**Розклад спринтів:** Sprint = 1 тиждень; Planning (1–2 год), Daily (15 min), Review (30 min), Retrospective (30 min).

## Інструкція: як закрити лабораторну (покроково)
1. Створити репозиторій на GitHub: `lab-Danya-expense-tracker`.
2. Скопіювати у корінь репо файли з цього набору (TЗ.md, VERSIONING.md, ...).
3. Ініціалізувати git, створити гілки `develop` і `main`.

### Рекомендовані команди (копіюй-встав):
```bash
# ініціалізація
git init
git add .
git commit -m "chore: add lab files (Expense Tracker)"
# створюємо потрібні гілки
git branch -M main
git checkout -b develop
# пуш на GitHub (створи репо онлайн, потім підстав URL)
git remote add origin <URL>
git push -u origin develop
git push -u origin main
```

### Демонстрація Git (приклад):
```bash
# створюємо фічу
git checkout -b feature/add-csv-export develop
# робимо зміни (наприклад, додаємо код або оновлюємо файли)
git add .
git commit -m "feat(export): add CSV export"
git push origin feature/add-csv-export
# створюємо Pull Request, після рев'ю зливаємо у develop
# після підготовки релізу:
git checkout main
git merge --no-ff develop
git tag -a v1.0.0 -m "Release v1.0.0"
git push origin main --tags
```

## Готовий звіт/презентація
Якщо хочеш, я можу згенерувати короткий звіт (PDF) на 1–2 сторінки, який ти зможеш завантажити в Moodle.

# VERSIONING.md — Політика версіонування та Git-стратегія

## Семантичне версіонування (SemVer)
Маємо формат **MAJOR.MINOR.PATCH**:
- **MAJOR** — сумісність зламано (breaking changes), наприклад, зміна структури API або міграція БД, яка не сумісна назад.
- **MINOR** — додається нова функціональність без порушення існуючих API (наприклад, додана можливість експортувати в JSON).
- **PATCH** — виправлення багів, не змінює API.

**Правила:**
- Перший реліз — `v1.0.0` коли MVP готовий та пройшов acceptance.
- Для hotfix-ів — підвищуємо PATCH: `1.0.0 -> 1.0.1`.
- Для додавання фіч — підвищуємо MINOR: `1.0.1 -> 1.1.0`.
- Для несумісних змін — підвищуємо MAJOR: `1.1.0 -> 2.0.0`.

## Git-стратегія — Simplified GitFlow
Гілки:
- `main` — тільки стабільні релізи (тегуються як `vX.Y.Z`).
- `develop` — інтеграційна гілка для підготовки релізів.
- `feature/<name>` — гілки для функціоналу, від `develop`.
- `hotfix/<name>` — від `main` для критичних виправлень.

**Приклад робочого процесу:**
```bash
git checkout -b feature/add-csv-export develop
# робота локально
git add .
git commit -m "feat(export): add CSV export for transactions"
git push origin feature/add-csv-export
# створюємо Pull Request, після рев'ю зливаємо у develop
```

**Підготовка релізу:**
1. Створити `release/1.0.0` з `develop` (опціонально).
2. Провести тестування, змерджити у `main`.
3. Створити тег: `git tag -a v1.0.0 -m "Release v1.0.0"` → `git push origin v1.0.0`.

---
name: konsol-design-system
description: Применяет source-backed дизайн-систему «Консоль» к B2B-интерфейсам онбординга, исполнителей, заданий, выплат, документов и рисков.
user-invocable: true
---

# Консоль Design System

## What is inside

- `README.md` — контекст продукта, состав пакета, Preview Manifest и reuse workflow.
- `DESIGN.md` — канонические визуальные и продуктовые правила.
- `colors_and_type.css` — токены и базовые классы.
- `preview/` — focused review cards.
- `assets/` — исходная презентация и representative media.
- `ui_kits/app/` — запускаемый applied UI-kit.
- `system/` — исторические extractor-токены и артефакты.

Проверяйте также `build/`, `fonts/` и `source_examples/`, если они появятся в будущей версии пакета. В текущей версии их нет, потому что источник не содержит соответствующих runtime-файлов, font-файлов или production-кода.

## Source context

Главный источник — `assets/Untitled.pptx`. Он подтверждает бренд «Консоль», типографику Graphik/CoFo Sans Mono, фирменные цвета, wordmark, фотографии и продуктовые модули. `context/source-context.md` фиксирует отсутствие связанных GitHub-репозиториев, local code folders, Figma и URL. Подробная доказательная запись: `context/pptx-evidence.md`.

## When to use this skill

Используйте навык для административных интерфейсов «Консоли», реестров исполнителей, карточек профиля, потоков выплат, документов, заданий, risk monitoring и marketplace. Не используйте его как универсальную тему для другого бренда.

## How to use

1. Полностью прочитайте `README.md` и `DESIGN.md`.
2. Подключите `colors_and_type.css`.
3. Просмотрите релевантные файлы в `preview/`.
4. Проверьте реальные файлы в `assets/`; при наличии будущих `build/`, `fonts/` и `source_examples/` изучите их до генерации.
5. Для app shell начните с `ui_kits/app/README.md`, затем прочитайте все файлы `ui_kits/app/components/` и композицию `index.html`.
6. Соблюдайте action economy, 8 px grid, доступность и mobile-рекомпозицию.
7. Любое новое правило сначала фиксируйте в `DESIGN.md`, затем синхронизируйте CSS и previews.

## Design system highlights

Color, typography, spacing, radius, layout and interaction rules are source-backed and must remain synchronized.

- Белая бумага, чёрный текст, один фиолетовый акцент.
- Крупный Graphik display и моноширинные CoFo-подписи.
- Плоские карточки, граница 1 px, радиус 8 px.
- Статус → причина → действие → следующий шаг.
- Source-backed модули: исполнители, задания, выплаты, документы, риски и маркетплейс.
- Реальные медиа сохраняются, а отсутствие production-кода явно маркируется.

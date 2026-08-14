# Консоль Design System

Переиспользуемый пакет для интерфейсов платформы «Консоль»: токены, правила, focused-превью и рабочий модульный UI‑kit.

## Product Overview

«Консоль» — цифровая B2B-платформа для работы компаний с самозанятыми, физлицами и ИП. Источник подтверждает продуктовые поверхности для онбординга исполнителей, проверки документов, электронных договоров и актов, постановки заданий, массовых выплат, чеков, мониторинга налоговых рисков и маркетплейса исполнителей.

This product is a business operations platform that supports contractor onboarding, documents, tasks, payouts, risk monitoring and marketplace workflows.

Ключевая интерфейсная задача — сделать юридически и финансово сложные процессы обозримыми: показывать статус, причину, действие и следующий шаг. Основной source reference — [assets/Untitled.pptx](assets/Untitled.pptx). Детали происхождения зафиксированы в [PROVENANCE.md](PROVENANCE.md) и [context/pptx-evidence.md](context/pptx-evidence.md).

## Sources

- `assets/Untitled.pptx` — исходная презентация на 39 слайдов.
- `assets/source-media/` — representative set медиа, извлечённый без перерисовки.
- `context/source-context.md` — intake-контракт; GitHub, local code, Figma и URL не подключены.
- `system/` — ранее сгенерированные токены и showcase-файлы; используются как исторический baseline, но `DESIGN.md` является каноном.

## Package Contents

- `DESIGN.md` — канонические правила продукта, цвета, типографика, layout, компоненты, motion, voice и anti-patterns.
- `colors_and_type.css` — reusable CSS tokens и базовые компонентные примитивы.
- `SKILL.md` — agent-usable инструкция по применению.
- `PROVENANCE.md` — происхождение, ограничения и контроль честности.
- `assets/` — исходная презентация и сохранённые медиа.
- `preview/` — небольшие focused review cards.
- `ui_kits/app/` — запускаемый React/Babel UI-kit рабочего пространства.
- `system/` — расширенные generated tokens и исторические артефакты extractor-проекта.

Папки `build/`, `fonts/` и `source_examples/` не созданы: в источнике нет runtime build-assets, встроенных font-файлов или production-компонентного кода. Это намеренное отсутствие, а не пропуск.

## Preview Manifest

| Путь | Что проверить | Что демонстрирует |
| --- | --- | --- |
| `preview/colors-primary.html` | иерархию базовых ролей | шесть канонических токенов |
| `preview/colors-theme-light.html` | контраст светлой темы | background, surface, border, accent |
| `preview/colors-theme-dark.html` | ограниченную тёмную поверхность | source-backed `#251d35`, белый текст и фиолетовый акцент |
| `preview/typography-specimens.html` | кириллицу, масштабы и fallback | Graphik/CoFo stacks и типографическую шкалу |
| `preview/spacing-tokens.html` | ритм и плотность | 8 px baseline и шкалу интервалов |
| `preview/spacing-radius.html` | форму компонентов | radius 8 px и pill-исключение |
| `preview/spacing-shadows.html` | плоскую и плавающую высоту | границы прежде теней |
| `preview/components-buttons.html` | default/hover/focus/disabled | primary, secondary, ghost и action economy |
| `preview/components-inputs.html` | label, help, error и focus | поля, select и поиск |
| `preview/brand-assets.html` | фактические файлы бренда | wordmark, портрет, hero и фирменную кривую из `assets/source-media/` |
| `preview/email-light.html` | структуру CRM-дайджеста и mobile fallback | сохранённый Figma-макет, email-модули и типографическое исключение Arial |

Manifest синхронизирован с фактическими HTML-файлами в `preview/`.

## Reuse Workflow

Inspect the source, review the focused cards, load the tokens and compose only the modules needed for the new artifact.

1. Прочитайте `DESIGN.md` и выберите релевантную продуктовую поверхность.
2. Подключите `colors_and_type.css` до локальных стилей.
3. Откройте focused card из `preview/`, соответствующую вашей задаче.
4. Для рабочего пространства начните с `ui_kits/app/index.html` и композиции в `ui_kits/app/components/`.
5. Сохраняйте одну primary CTA на действие и перестраивайте таблицы в карточки на mobile.
6. Не выдавайте реконструкцию UI-kit за production-код: исходный код продукта не был предоставлен.

## Быстрый старт

```html
<link rel="stylesheet" href="colors_and_type.css">
<button class="ds-button ds-button--primary">Добавить исполнителя</button>
```

## Контроль изменений

- Любое изменение визуального правила сначала вносится в `DESIGN.md`.
- Затем синхронизируются `colors_and_type.css`, affected preview cards и UI-kit.
- Новые реальные ассеты сохраняются с provenance; существующие файлы не перерисовываются.
- При появлении production-кода high-signal компоненты копируются в `source_examples/` без упрощения.

# UI Kit: рабочее пространство «Консоль»

Запускаемый applied interface kit для desktop и responsive web. Он реконструирует подтверждённые в `Untitled.pptx` поверхности: навигацию, реестр исполнителей, задания, выплаты и risk monitoring.

## Structure

- `index.html` — browser entry: React 18.3.1, ReactDOM 18.3.1, Babel 7.29.0, глобальные JSX-компоненты и mount в `#root`.
- `app.css` — layout, responsive-поведение и компонентные состояния.
- `components/Sidebar.jsx` — основная навигация и mobile rail.
- `components/SummaryCards.jsx` — source-backed operational overview.
- `components/ContractorsTable.jsx` — поиск и адаптивный реестр исполнителей.
- `components/PayoutFlow.jsx` — этапы акта, оплаты, чека и налоговой копилки.
- `components/RiskPanel.jsx` — понятное представление риск-факторов.
- `components/App.jsx` — композиция shell и интерактивных модулей.

## Usage

Open `index.html`, use the loaded components, compose the required modules and build the adapted surface. Все компоненты напрямую загружаются как `text/babel` и публикуют себя в `window`. `App.jsx` собирает интерфейс и рендерится через `ReactDOM.createRoot`.

Для новой поверхности сохраните shell и замените только содержательную область. Подключение `../../colors_and_type.css` обязательно; локальный `app.css` не должен переопределять канонические роли цвета и шрифтов.

## Design Notes

- Sidebar 248 px на desktop, горизонтальный rail до 820 px.
- Одна primary CTA — «Добавить исполнителя».
- Реестр превращается в карточки на mobile и не создаёт горизонтальный scroll.
- Статус всегда подписан текстом; цвет не является единственным носителем значения.
- Risk panel содержит причину и действие без тревожной полноэкранной заливки.

## Source

UI-kit основан на продуктовых модулях и значениях со слайдов: 245 исполнителей, 1 600 заданий, записи Петрова, Николаевой и Ивлева, а также поток «акт → оплата → чек → налоговая копилка». Production-код не был предоставлен, поэтому это source-backed реконструкция, а не копия приложения.

# Drift — Design System

**Дата:** 2026-03-29
**Автор:** Скай (creative-дизайнер OpenClaw)
**Основа:** [spec.md](spec.md), [research.md](research.md)

---

## 1. Визуальная концепция

### Философия

Drift — антитеза агрессивным трекерам. Никакого "ты провалился". Интерфейс должен ощущаться как тёплое одеяло, а не как табло с результатами экзамена. Лена (тревожная отличница) открывает приложение и чувствует спокойствие, а не давление.

### Стиль

- **Мягкий, скруглённый, воздушный.** Никаких острых углов, жёстких границ, контрастных разделителей.
- **Много воздуха.** Padding и margin щедрые. Элементы дышат.
- **Типографика — округлая, дружелюбная.** Inter с font-weight 400/500/600 (не 700+). Крупные размеры, высокий line-height.

### Вдохновение

| Референс | Что берём |
|---|---|
| Bears Gratitude | Мягкость форм, тёплая палитра, ощущение уюта |
| Calm | Спокойный ритм, минимум элементов, плавные анимации |
| Headspace | Минимализм, крупные кнопки, один экран = одно действие |

---

## 2. Палитра

### Принцип: НЕ красный/зелёный

Красный = ошибка, стресс. Зелёный = "правильно/неправильно". Это бинарная система оценки, от которой Drift уходит. Вместо этого — пастельные, тёплые, небинарные цвета.

### Светлая тема (основная)

| Токен | HEX | Назначение |
|---|---|---|
| `--color-bg` | `#FBF8F4` | Фон страницы. Тёплый off-white, не стерильный. |
| `--color-surface` | `#FFFFFF` | Фон карточки. Чистый белый с тенью. |
| `--color-text-primary` | `#3D3A37` | Основной текст. Тёмно-коричневый, не чёрный. |
| `--color-text-secondary` | `#9B9590` | Вторичный текст, подписи. |
| `--color-text-phrase` | `#7B6F65` | Позитивная фраза. Чуть ярче secondary. |
| `--color-accent-lavender` | `#C4B5E0` | Momentum 0-30%. Спокойный лавандовый. |
| `--color-accent-mint` | `#A8D8C8` | Momentum 31-60%. Мятный, свежий. |
| `--color-accent-peach` | `#F5C6A5` | Momentum 61-80%. Персиковый, тёплый. |
| `--color-accent-apricot` | `#F0A878` | Momentum 81-99%. Насыщенный абрикосовый. |
| `--color-accent-gold` | `#E8B84B` | Momentum 100%. Золотой, торжественный. |
| `--color-dot-done` | `#D4C4A0` | Тепловая карта: отмеченный день. Тёплый песочный. |
| `--color-dot-missed` | `#E8E4DF` | Тепловая карта: пропущенный день. Бледный серый. |
| `--color-dot-today` | `#C4B5E0` | Тепловая карта: сегодня (если не отмечен). Лавандовый контур. |
| `--color-button-bg` | `#E8DDD0` | Фон кнопки "Сделано" (до нажатия). |
| `--color-button-bg-active` | `#D4C4A0` | Фон кнопки "Сделано" (после нажатия / сегодня уже отмечено). |
| `--color-button-text` | `#5C544B` | Текст кнопки. |
| `--color-shadow` | `rgba(61, 58, 55, 0.06)` | Тень карточки. |

### Тёмная тема

| Токен | HEX | Назначение |
|---|---|---|
| `--color-bg` | `#1C1A18` | Фон страницы. Тёплый тёмно-коричневый. |
| `--color-surface` | `#2A2725` | Фон карточки. |
| `--color-text-primary` | `#E8E4DF` | Основной текст. |
| `--color-text-secondary` | `#8A837D` | Вторичный текст. |
| `--color-text-phrase` | `#B0A89E` | Позитивная фраза. |
| `--color-accent-lavender` | `#9B88C4` | Momentum 0-30%. |
| `--color-accent-mint` | `#7AB8A4` | Momentum 31-60%. |
| `--color-accent-peach` | `#D4A07A` | Momentum 61-80%. |
| `--color-accent-apricot` | `#C88A58` | Momentum 81-99%. |
| `--color-accent-gold` | `#D4A43C` | Momentum 100%. |
| `--color-dot-done` | `#A09070` | Отмеченный день. |
| `--color-dot-missed` | `#3A3633` | Пропущенный день. |
| `--color-dot-today` | `#9B88C4` | Сегодня (не отмечен). |
| `--color-button-bg` | `#3A3633` | Кнопка (до нажатия). |
| `--color-button-bg-active` | `#5C544B` | Кнопка (после нажатия). |
| `--color-button-text` | `#E8E4DF` | Текст кнопки. |
| `--color-shadow` | `rgba(0, 0, 0, 0.2)` | Тень карточки. |

### Определение темы

```css
@media (prefers-color-scheme: dark) {
  :root { /* тёмные токены */ }
}
```

---

## 3. Типографика

| Элемент | Шрифт | Размер | Вес | Line-height | Letter-spacing |
|---|---|---|---|---|---|
| Название привычки | Inter | `24px` | 500 | `1.3` | `-0.01em` |
| Momentum % | Inter | `48px` | 600 | `1.0` | `-0.02em` |
| Позитивная фраза | Inter | `16px` | 400 | `1.5` | `0` |
| Кнопка "Сделано" | Inter | `18px` | 500 | `1.0` | `0.02em` |
| Подписи дней (пн, вт...) | Inter | `11px` | 400 | `1.0` | `0.04em` |

Подключение:

```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600&display=swap');
```

---

## 4. Momentum Meter (центральный элемент)

### Конструкция

Круговой прогресс-бар на SVG. Окружность `stroke-dasharray` / `stroke-dashoffset`.

| Параметр | Значение |
|---|---|
| Диаметр (viewBox) | `200` единиц |
| Размер на экране | `200px` (mobile), `240px` (desktop) |
| Толщина трека (фон) | `stroke-width: 10` |
| Толщина прогресса | `stroke-width: 10` |
| Цвет трека | `--color-dot-missed` (бледный) |
| stroke-linecap | `round` |
| Начальная позиция | 12 часов (top), по часовой стрелке |
| Радиус окружности | `90` (чтобы stroke не обрезался) |
| Длина окружности | `2 * pi * 90 = 565.49` |

### Цвет прогресса по уровню

Цвет меняется **плавно** через CSS transition. В каждый момент используется один цвет, определяемый уровнем momentum:

| Momentum | Цвет | Токен |
|---|---|---|
| 0% | `--color-accent-lavender` | Лавандовый — спокойный старт |
| 1-30% | `--color-accent-lavender` | Лавандовый |
| 31-60% | `--color-accent-mint` | Мятный |
| 61-80% | `--color-accent-peach` | Персиковый |
| 81-99% | `--color-accent-apricot` | Абрикосовый |
| 100% | `--color-accent-gold` | Золотой |

### Анимация

```css
.momentum-progress {
  transition: stroke-dashoffset 800ms cubic-bezier(0.4, 0, 0.2, 1),
              stroke 600ms ease-in-out;
}
```

- Заполнение: `800ms`, ease-out. Плавное "наливание", не рывок.
- Смена цвета: `600ms`, мягкий переход между уровнями.

### Текст внутри

- Число `XX%` — по центру круга, `48px`, weight 600.
- Под числом ничего нет (фраза вынесена ниже).

### Состояние 0%

Круг полностью заполнен треком (бледный цвет). Текст: `0%`. Фраза ниже: "Первый шаг -- самый важный". Никакого ощущения пустоты или провала.

---

## 5. Кнопка "Сделано"

### Размеры

| Параметр | Значение |
|---|---|
| Ширина | `100%` от карточки (с padding) |
| Максимальная ширина | `280px` |
| Высота | `56px` |
| Border-radius | `16px` |
| Минимальный touch target | `48px` (соответствует WCAG) |

### Состояния

**Не нажата (сегодня не отмечено):**

```css
.btn-done {
  background: var(--color-button-bg);
  color: var(--color-button-text);
  border: none;
  border-radius: 16px;
  font-size: 18px;
  font-weight: 500;
  letter-spacing: 0.02em;
  cursor: pointer;
  transition: transform 150ms ease, background 200ms ease, box-shadow 200ms ease;
  box-shadow: 0 2px 8px var(--color-shadow);
}
```

**Hover / focus:**

```css
.btn-done:hover {
  transform: scale(1.02);
  box-shadow: 0 4px 16px var(--color-shadow);
}

.btn-done:focus-visible {
  outline: 2px solid var(--color-accent-lavender);
  outline-offset: 3px;
}
```

**Нажатие (active):**

```css
.btn-done:active {
  transform: scale(0.97);
}
```

**После отметки (сегодня сделано):**

```css
.btn-done--completed {
  background: var(--color-button-bg-active);
  color: var(--color-button-text);
}
```

Текст меняется: "Сделано" -> "Готово!" (или галочка). Повторное нажатие = undo.

### Анимация при нажатии

1. **Пульсация** (scale): `0.97 -> 1.0`, `150ms ease`.
2. **Частицы**: 6-8 маленьких кружков (4px) разлетаются из центра кнопки радиально, `400ms`, fade out. Цвет частиц = текущий цвет momentum.
3. **Тактильный feedback**: `navigator.vibrate(10)` (если поддерживается).
4. **Momentum meter обновляется** с анимацией `800ms` после нажатия.

Спецификация частиц:

```css
@keyframes particle-burst {
  0% {
    opacity: 1;
    transform: translate(0, 0) scale(1);
  }
  100% {
    opacity: 0;
    transform: translate(var(--dx), var(--dy)) scale(0.5);
  }
}

.particle {
  position: absolute;
  width: 6px;
  height: 6px;
  border-radius: 50%;
  animation: particle-burst 400ms ease-out forwards;
  pointer-events: none;
}
```

Каждая частица получает `--dx` и `--dy` через inline style, рандомизированные в диапазоне `-40px..+40px`.

---

## 6. Тепловая карта (30 дней)

### Конструкция

Горизонтальная строка из 30 кружков. Слева = 30 дней назад, справа = сегодня.

| Параметр | Значение |
|---|---|
| Кол-во точек | 30 (скользящее окно) |
| Диаметр точки | `10px` |
| Gap между точками | `6px` |
| Общая ширина | `30 * 10 + 29 * 6 = 474px` (с overflow-x: auto на маленьких экранах) |
| Контейнер | `display: flex; gap: 6px; justify-content: center; flex-wrap: wrap;` |

На экранах < 474px точки переносятся на вторую строку (flex-wrap). Альтернатива: уменьшить размер точек.

**Адаптивность:**

```css
/* Mobile < 400px */
@media (max-width: 399px) {
  .heatmap-dot {
    width: 8px;
    height: 8px;
  }
  .heatmap {
    gap: 4px;
  }
}
```

### Состояния точки

| Состояние | Стиль |
|---|---|
| Отмечен | `background: var(--color-dot-done); transform: scale(1);` |
| Пропущен | `background: var(--color-dot-missed); transform: scale(1);` |
| Сегодня (не отмечен) | `background: transparent; border: 2px solid var(--color-dot-today);` |
| Сегодня (отмечен) | `background: var(--color-dot-done); border: 2px solid var(--color-dot-today);` |
| Будущие дни | Не отображаются |

### Анимация при отметке

Точка "сегодня" при нажатии кнопки "Сделано":

```css
@keyframes dot-fill {
  0% { transform: scale(0.5); opacity: 0.3; }
  50% { transform: scale(1.3); }
  100% { transform: scale(1); opacity: 1; }
}

.heatmap-dot--today.heatmap-dot--done {
  animation: dot-fill 400ms ease-out;
}
```

---

## 7. Позитивная фраза

### Расположение

Под momentum meter, над кнопкой. Центрирована.

### Стиль

```css
.phrase {
  font-size: 16px;
  font-weight: 400;
  color: var(--color-text-phrase);
  text-align: center;
  line-height: 1.5;
  min-height: 24px; /* предотвращает прыжки layout */
  transition: opacity 300ms ease;
}
```

### Фразы по уровню

| Momentum | Фраза |
|---|---|
| 0% | "Первый шаг -- самый важный" |
| 1-30% | "Начало положено" |
| 31-60% | "Набираешь обороты" |
| 61-80% | "Хорошая инерция" |
| 81-99% | "Ты в потоке" |
| 100% | "Полный momentum" |

### Смена фразы

При изменении уровня: fade out `150ms` -> смена текста -> fade in `150ms`. Суммарно `300ms`. Не должна меняться чаще чем раз в секунду.

### Принцип

Фраза всегда позитивная или нейтральная. Даже при 0% -- это приглашение, не упрёк. "Первый шаг -- самый важный" звучит мягко и ободряюще.

---

## 8. Структура экрана

### Layout

```
+------------------------------------------+
|              [фон: --color-bg]           |
|                                          |
|   +----------------------------------+   |
|   |         Название привычки        |   |  <- редактируемое, tap to edit
|   |              (24px)              |   |
|   |                                  |   |
|   |       +-----------------+        |   |
|   |       |                 |        |   |
|   |       |   MOMENTUM      |        |   |  <- SVG circle, 200px
|   |       |     METER       |        |   |
|   |       |     67%         |        |   |
|   |       |                 |        |   |
|   |       +-----------------+        |   |
|   |                                  |   |
|   |      "Хорошая инерция"           |   |  <- фраза, 16px
|   |                                  |   |
|   |      +--------------------+      |   |
|   |      |     Сделано        |      |   |  <- кнопка, 56px high
|   |      +--------------------+      |   |
|   |                                  |   |
|   |   o o o o o o o o o o o o o o o  |   |  <- тепловая карта, 30 точек
|   |   o o o o o o o o o o o o o o o  |   |
|   |                                  |   |
|   +----------------------------------+   |
|                                          |
+------------------------------------------+
```

### CSS-каркас карточки

```css
.card {
  background: var(--color-surface);
  border-radius: 24px;
  padding: 40px 32px 32px;
  max-width: 380px;
  width: calc(100% - 32px);
  margin: 0 auto;
  box-shadow: 0 4px 24px var(--color-shadow);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 24px;
}
```

### Центрирование на странице

```css
body {
  display: flex;
  justify-content: center;
  align-items: center;
  min-height: 100dvh;
  margin: 0;
  padding: 16px;
  background: var(--color-bg);
  font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;
  -webkit-font-smoothing: antialiased;
}
```

### Spacing между элементами (gap внутри карточки)

| Между | Расстояние |
|---|---|
| Название -> Momentum meter | `24px` |
| Momentum meter -> Фраза | `16px` |
| Фраза -> Кнопка | `24px` |
| Кнопка -> Тепловая карта | `28px` |

Реализация: `gap: 24px` на flex-контейнере + переопределение через margin-top для нестандартных отступов.

---

## 9. Reduced Motion

Для пользователей с `prefers-reduced-motion: reduce`:

```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
  }

  .btn-done:hover {
    transform: none;
  }

  .btn-done:active {
    transform: none;
  }

  .particle {
    display: none;
  }
}
```

Все анимации отключаются. Визуальная информация остаётся, только без движения. Частицы скрываются полностью.

---

## 10. Responsive

### Breakpoints

| Breakpoint | Экран | Что меняется |
|---|---|---|
| `< 375px` | Маленькие телефоны | Карточка padding: `32px 20px 24px`. Momentum meter: `160px`. Кнопка: `48px` высота. |
| `375px - 767px` | Телефоны (основной) | Дефолтные размеры. Карточка: `380px` max-width. |
| `768px+` | Планшет/десктоп | Momentum meter: `240px`. Карточка: `420px` max-width. |

### Mobile-first CSS

```css
/* Base: mobile 375px */
.momentum-meter { width: 200px; height: 200px; }

/* Small phones */
@media (max-width: 374px) {
  .momentum-meter { width: 160px; height: 160px; }
  .card { padding: 32px 20px 24px; }
  .btn-done { height: 48px; font-size: 16px; }
}

/* Tablets and desktop */
@media (min-width: 768px) {
  .momentum-meter { width: 240px; height: 240px; }
  .card { max-width: 420px; padding: 48px 40px 40px; }
}
```

---

## 11. Название привычки (редактируемое)

### Отображение

```css
.habit-name {
  font-size: 24px;
  font-weight: 500;
  color: var(--color-text-primary);
  text-align: center;
  line-height: 1.3;
  letter-spacing: -0.01em;
  border: none;
  background: none;
  width: 100%;
  padding: 4px 8px;
  border-radius: 8px;
  transition: background 200ms ease;
}

.habit-name:hover {
  background: var(--color-dot-missed); /* лёгкая подсветка, hint на редактируемость */
}

.habit-name:focus {
  outline: none;
  background: var(--color-dot-missed);
}
```

Реализация через `<input>` или `contenteditable` div. Placeholder: "Моя привычка".

### Сброс привычки

Долгий тап (500ms) на названии -> модальное окно подтверждения:

```css
.modal-overlay {
  position: fixed;
  inset: 0;
  background: rgba(61, 58, 55, 0.4);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 100;
  animation: fade-in 200ms ease;
}

.modal {
  background: var(--color-surface);
  border-radius: 20px;
  padding: 32px;
  max-width: 320px;
  width: calc(100% - 48px);
  text-align: center;
  box-shadow: 0 8px 32px rgba(0, 0, 0, 0.12);
}
```

---

## 12. Первый запуск (Onboarding)

При первом открытии (нет данных в localStorage):

1. Фон страницы, без карточки.
2. По центру: "Какую привычку ты хочешь развить?"
3. Текстовое поле, placeholder: "Например: медитация"
4. Кнопка "Начать".

Стиль текстового поля:

```css
.onboarding-input {
  font-size: 20px;
  font-weight: 400;
  color: var(--color-text-primary);
  background: var(--color-surface);
  border: 2px solid var(--color-dot-missed);
  border-radius: 14px;
  padding: 16px 20px;
  width: 100%;
  max-width: 300px;
  text-align: center;
  transition: border-color 200ms ease;
}

.onboarding-input:focus {
  outline: none;
  border-color: var(--color-accent-lavender);
}
```

---

## Сводка токенов (CSS custom properties)

```css
:root {
  /* Palette — light */
  --color-bg: #FBF8F4;
  --color-surface: #FFFFFF;
  --color-text-primary: #3D3A37;
  --color-text-secondary: #9B9590;
  --color-text-phrase: #7B6F65;

  --color-accent-lavender: #C4B5E0;
  --color-accent-mint: #A8D8C8;
  --color-accent-peach: #F5C6A5;
  --color-accent-apricot: #F0A878;
  --color-accent-gold: #E8B84B;

  --color-dot-done: #D4C4A0;
  --color-dot-missed: #E8E4DF;
  --color-dot-today: #C4B5E0;

  --color-button-bg: #E8DDD0;
  --color-button-bg-active: #D4C4A0;
  --color-button-text: #5C544B;

  --color-shadow: rgba(61, 58, 55, 0.06);

  /* Typography */
  --font-family: 'Inter', -apple-system, BlinkMacSystemFont, sans-serif;

  /* Sizes */
  --momentum-size: 200px;
  --card-max-width: 380px;
  --card-padding: 40px 32px 32px;
  --card-radius: 24px;
  --button-height: 56px;
  --button-radius: 16px;
  --dot-size: 10px;
  --dot-gap: 6px;

  /* Animation */
  --timing-momentum: 800ms;
  --timing-color: 600ms;
  --timing-button: 150ms;
  --timing-particle: 400ms;
  --timing-phrase: 300ms;
  --easing-momentum: cubic-bezier(0.4, 0, 0.2, 1);
  --easing-default: ease;
}

@media (prefers-color-scheme: dark) {
  :root {
    --color-bg: #1C1A18;
    --color-surface: #2A2725;
    --color-text-primary: #E8E4DF;
    --color-text-secondary: #8A837D;
    --color-text-phrase: #B0A89E;

    --color-accent-lavender: #9B88C4;
    --color-accent-mint: #7AB8A4;
    --color-accent-peach: #D4A07A;
    --color-accent-apricot: #C88A58;
    --color-accent-gold: #D4A43C;

    --color-dot-done: #A09070;
    --color-dot-missed: #3A3633;
    --color-dot-today: #9B88C4;

    --color-button-bg: #3A3633;
    --color-button-bg-active: #5C544B;
    --color-button-text: #E8E4DF;

    --color-shadow: rgba(0, 0, 0, 0.2);
  }
}
```

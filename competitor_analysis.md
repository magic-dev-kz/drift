# RECON: Конкурентный анализ Drift

**Агент:** Молот
**Дата:** 2026-03-29
**Объект:** Drift — gentle habit tracker ("no streaks, no guilt, just momentum")
**URL:** https://magic-dev-kz.github.io/drift/

---

## 1. Drift: что есть сейчас (v1)

| Параметр | Значение |
|---|---|
| Привычки | 1 (by design) |
| Механика | 30-day sliding window momentum (0-100%) |
| Визуализация | SVG progress ring + 30-dot heatmap |
| Хранение | localStorage (браузер) |
| Платформа | Web (single HTML file, PWA) |
| Цена | Бесплатно |
| Уведомления | Нет |
| Виджеты | Нет |
| Экспорт | Нет |
| Cloud sync | Нет |
| Аналитика | Нет (только momentum %) |
| Мульти-устройства | Нет |

**Уникальное:** Momentum вместо streaks. Пропуск = замедление, не обнуление. Позитивные фразы вместо "Streak: 0 days". Минимализм до предела.

---

## 2. Прямые конкуренты

### 2.1 Streaks ($5.99 one-time)

- **Apple Design Award winner.** Золотой стандарт iOS habit tracking.
- До 24 привычек с 600+ иконками и 78 цветовыми темами
- Глубокая интеграция с Apple Health (автотрекинг шагов, сна и т.д.)
- Apple Watch, iPad, Mac, Vision Pro
- iCloud sync между устройствами
- Виджеты на Home Screen
- Напоминания (включая haptic на Apple Watch)
- Приватность: нет аккаунта, данные на устройстве + iCloud
- **Нет:** data export, web-версии, Android

**Вердикт:** Главный конкурент по качеству. Но полностью streak-based — обнуление при пропуске. Это именно та боль, которую решает Drift.

### 2.2 Habitica (бесплатно / $4.99-$47.99 подписка)

- RPG gamification: 8-bit аватар, квесты, партии, экипировка
- Три типа задач: Habits, Dailies, To-Dos
- Пропуск = урон здоровью персонажа (буквальное наказание)
- Социальный: партии, челленджи, гильдии
- Web + iOS + Android
- Premium = косметика, не функции (щедрый free tier)
- **Нет:** виджетов, Apple Health интеграции, минимализма

**Вердикт:** Полная противоположность Drift по философии. Habitica НАКАЗЫВАЕТ за пропуск (урон персонажу). Для "тревожной отличницы Лены" — это кошмар.

### 2.3 Atoms ($10/мес или $70/год, 28 дней бесплатно)

- Официальное приложение от James Clear (Atomic Habits)
- Ежедневные уроки от автора книги
- Детальная аналитика и инсайты
- Напоминания (несколько на привычку)
- Apple Watch
- Free tier: 1 привычка (как у Drift!)
- **Самый дорогой** в категории

**Вердикт:** Ближайший идеологический сосед. Тоже про "маленькие шаги". Но $120/год за трекер привычек — агрессивный прайсинг. Free tier с 1 привычкой = прямое пересечение с Drift. Но Atoms всё равно streak-based.

### 2.4 Done ($24.99-$499.99 lifetime, частые скидки до 95%)

- Готовые шаблоны привычек + кастомные
- Виджеты (Home Screen + Apple Watch)
- Тренды: weekly/monthly/yearly графики
- CSV export
- **Напоминания только в Premium**
- Безлимитные привычки в Premium
- iOS only

**Вердикт:** Хороший функционал, но ценообразование странное. $499.99 "lifetime" при постоянных скидках 95% = маркетинговый трюк. Streak-based.

### 2.5 Tangerine ($2.49/мес yearly или $4.99/мес)

- Привычки + настроение + журнал в одном
- Mood-habit корреляция (уникальная фича!)
- Организация по времени дня (утро/день/вечер)
- Безлимитные привычки даже на free tier
- Виджеты, напоминания
- iOS + Android
- 7-дневный trial на годовой подписке

**Вердикт:** Самый "мягкий" из mainstream трекеров. Mood tracking + habits = интересная комбинация. Но всё равно streak-ориентирован.

### 2.6 Strides ($4.99/мес или $39.99/год)

- 4 типа трекеров: Habit, Target, Average, Project
- 150+ шаблонов
- Apple Health интеграция
- Прогресс-бары, success rates, графики
- Data export
- Free: 3 трекера
- iOS only (Mac скоро)

**Вердикт:** Самый "аналитический" трекер. Тип "Average" (rolling mean) — концептуально близок к momentum Drift. Но UX перегружен для минималиста.

### 2.7 Snowball / Habit (Snowball)

Не найден как отдельный habit tracker. Snowball Analytics — это инвестиционный трекер. Возможно, имелся в виду другой продукт или он прекратил существование.

---

## 3. "No Guilt" ниша: кто ещё здесь?

### Прямые обитатели ниши

| Приложение | Философия | Цена | Статус |
|---|---|---|---|
| **Gentle Habits** | "No red X's, no streak anxiety". Мягкие цвета, wins > misses | Неизвестна (вероятно freemium) | Новое (2025-2026), App Store |
| **Couch Habits** | "Expects nothing from you". No guilt, no pressure. ADHD-friendly | Бесплатно | Нишевое, минималистичное |
| **LifePace** | Skipped day не ломает streak (опционально) | Неизвестна | App Store |
| **Aura** | "Celebrates what you did, not what you missed" | Неизвестна | App Store |
| **Uncluttered** | Можно пропускать без вины, research-backed | Неизвестна | App Store |
| **Drift** | 30-day momentum window, пропуск = замедление | Бесплатно (web) | Наш продукт |

### Ключевой вывод

**Ниша "no guilt" растёт, но НЕ занята лидером.** Вот почему:

1. **Gentle Habits** и **Couch Habits** — свежие (2025-2026), что подтверждает тренд
2. Ни один из "no guilt" трекеров не стал мейнстримом (нет их в топ-10 списках)
3. Mainstream трекеры (Streaks, Habitica, Done) по-прежнему streak/punishment-based
4. Atoms — идеологически близок (Atomic Habits = маленькие шаги), но на практике тоже streak-based и стоит $120/год

**Drift имеет окно возможности.** Ниша валидирована (конкуренты появляются), но лидера нет. Механика momentum (30-day sliding window) — уникальна. Никто из конкурентов не использует именно скользящее окно с плавным затуханием.

---

## 4. Сравнение фич

| Фича | Drift | Streaks | Habitica | Atoms | Done | Tangerine | Strides | Gentle Habits | Couch |
|---|---|---|---|---|---|---|---|---|---|
| Привычек | 1 | 24 | Безлимит | Безлимит (paid) | Безлимит (paid) | Безлимит | 3 free / безлимит paid | Несколько | Несколько |
| No-guilt механика | **Momentum** | Нет | Нет (урон) | Нет | Нет | Нет | Нет | Мягкие цвета | Нет наказания |
| Sliding window | **30 дней** | Нет | Нет | Нет | Нет | Нет | Rolling avg (похоже) | Нет | Нет |
| Виджеты | Нет | Да | Нет | Нет | Да | Да | Да | Да | Нет |
| Напоминания | Нет | Да | Нет | Да | Paid | Да | Да | Нет инфо | Нет |
| Apple Watch | Нет | Да | Нет | Да | Да | Нет | Да | Нет инфо | Нет |
| Cloud sync | Нет | iCloud | Сервер | Сервер | Нет | Сервер | iCloud | Нет инфо | Нет |
| Data export | Нет | Нет | Нет | Нет | CSV (paid) | Нет | Да | Нет | Нет |
| Аналитика | % | Стрик | RPG stats | Детальная | Тренды | Mood+habits | Графики | Базовая | Нет |
| Web | **Да** | Нет | Да | Нет | Нет | Нет | Нет | Нет | Нет |
| Android | **Да (web)** | Нет | Да | Да | Нет | Да | Нет | Нет | Нет |
| Бесплатно | **Полностью** | $5.99 | Да | 28 дней / 1 привычка | Ограничено | Ограничено | 3 трекера | Неизвестно | Да |

---

## 5. Ценообразование

| Конкурент | Модель | Цена | Бесплатные фичи | Платные фичи |
|---|---|---|---|---|
| **Streaks** | One-time | $5.99 | Нет free tier | Всё включено навсегда |
| **Habitica** | Freemium | $0 / $4.99-$47.99 подписка | Все core-фичи бесплатно | Косметика, gems |
| **Atoms** | Subscription | $10/мес или $70/год | 1 привычка бесплатно | Безлимит привычек, уроки, аналитика |
| **Done** | Lifetime | $24.99-$499.99 (скидки) | Ограниченные привычки, нет напоминаний | Безлимит, напоминания, тренды, export |
| **Tangerine** | Subscription | $2.49/мес (yearly) или $4.99/мес | Безлимит привычек, mood, журнал | Insights, фото, шаблоны |
| **Strides** | Subscription | $4.99/мес или $39.99/год | 3 трекера | Безлимит, sync, export, отчёты |
| **Gentle Habits** | Неизвестна | - | - | - |
| **Couch Habits** | Free | $0 | Всё | - |
| **Drift** | Free | $0 | Всё | - (пока нет) |

### Вывод по ценам

- One-time purchase (Streaks) — самая честная модель, пользователи любят
- Подписки $3-5/мес — стандарт рынка
- Atoms $10/мес — премиум за бренд James Clear
- Free + Premium фичи — самый распространённый путь монетизации

---

## 6. Рекомендация: ТОП-5 фич для Drift v2

### Приоритет 1 (критично для роста)

**1. Multiple Habits (2-5 привычек)**
- Почему: Это причина номер 1, по которой пользователь уйдёт к конкуренту. Даже Atoms free даёт 1 привычку — но платный даёт безлимит. Drift с лимитом в 1 привычку = интересный эксперимент, но не daily driver.
- Как: Не безлимит (это Streaks). 3-5 привычек с тем же momentum ring для каждой. Общий "life momentum" как среднее.
- Риск: Потеря минимализма. Митигация: лимит 5, простой список, no categories.

**2. PWA Notifications (напоминания)**
- Почему: Без напоминаний привычка забывается. Это не фича, это необходимость. Конкуренты (Streaks, Atoms, Tangerine, Strides) все имеют.
- Как: PWA Push Notifications. Одно напоминание на привычку, выбор времени. Мягкий текст: "Привет! Не забудь про [привычку]" вместо "ТЫ ЕЩЁ НЕ СДЕЛАЛ".
- Риск: Низкий. Web Push API работает в Chrome/Edge/Safari.

### Приоритет 2 (конкурентное преимущество)

**3. Weekly Insights (мини-аналитика)**
- Почему: Пользователь хочет видеть прогресс во времени, не только текущий %. Tangerine и Strides сильны тут.
- Как: Простой недельный виджет: "На этой неделе: 5/7. Momentum вырос с 73% до 80%". Месячный тренд momentum (линия). Всё в том же одном экране.
- Риск: Перегрузка UI. Митигация: collapsible section, показывать по тапу.

### Приоритет 3 (retention + доверие)

**4. Data Export (JSON/CSV)**
- Почему: localStorage = данные могут пропасть. Пользователь не доверяет приложению без бэкапа. Плюс это бесплатный trust signal.
- Как: Кнопка "Экспорт" -> JSON файл с полной историей. Импорт из файла.
- Риск: Минимальный. 2-4 часа разработки.

**5. Home Screen Widget (PWA)**
- Почему: Drift живёт в браузере. Без виджета — нет визуального напоминания. Streaks, Done, Tangerine, Strides — все с виджетами.
- Как: PWA "Add to Home Screen" уже есть. Но полноценные виджеты (iOS/Android) требуют нативного приложения. Альтернатива: Shortcut/Bookmark с красивой иконкой + manifest.json.
- Риск: Ограничения PWA на iOS. Полноценный виджет потребует нативную обёртку.

---

## 7. Стратегические наблюдения

### Drift сильнее конкурентов в:
1. **Философии** — единственный с настоящим sliding window momentum. Не "мягкие цвета для пропуска", а математически другая модель.
2. **Доступности** — web = любая платформа, $0, без установки. Конкуренты привязаны к iOS.
3. **Простоте** — один HTML файл. Zero friction onboarding.

### Drift слабее конкурентов в:
1. **Функционале** — 1 привычка, нет напоминаний, нет аналитики, нет sync
2. **Долговечности данных** — localStorage может быть очищен браузером
3. **Дистрибуции** — нет в App Store/Play Store = нет органического discovery

### Возможность монетизации (v3+):
- **Freemium:** 3 привычки бесплатно, больше за $2.99/мес или $19.99/год
- **One-time:** $4.99 (как Streaks, но дешевле)
- Рекомендация: начать бесплатно, собрать аудиторию, добавить Premium позже

---

## 8. Итоговый вердикт

**Ниша "no guilt habit tracking" — валидирована и растёт.** Появление Gentle Habits, Couch Habits, Aura в 2025-2026 подтверждает тренд. Но лидера нет.

**Drift имеет уникальное конкурентное преимущество:** 30-day sliding window momentum — это не просто "мягкие слова". Это другая математическая модель, которая объективно справедливее к пользователю. Никто из конкурентов не делает именно так.

**Главный риск:** функциональный разрыв. 1 привычка + 0 напоминаний + 0 sync = красивый прототип, а не daily driver. Multiple habits и notifications — must have для v2.

**Прогноз:** Если Drift добавит 3-5 привычек + напоминания + базовую аналитику и попадёт в Product Hunt / Indie Hackers — есть шанс стать тем самым лидером ниши "gentle habits".

---

## Источники

- [Streaks App - App Store](https://apps.apple.com/us/app/streaks/id963034692)
- [Streaks Official Site](https://streaksapp.com/)
- [Habitica](https://habitica.com/)
- [Habitica Review 2026 - Calmevo](https://calmevo.com/habitica-review/)
- [Atoms - Official Atomic Habits App](https://atoms.jamesclear.com/)
- [Atoms - App Store](https://apps.apple.com/us/app/atoms-from-atomic-habits/id6474421906)
- [Done App Review 2026 - CRM.org](https://crm.org/news/done-app-review)
- [Tangerine App](https://tangerine.app/)
- [Tangerine - TechCrunch](https://techcrunch.com/2020/02/10/tangerines-pretty-self-care-app-combines-habit-and-mood-tracking-for-better-insights/)
- [Strides App](https://www.stridesapp.com/)
- [Strides Review 2026 - CRM.org](https://crm.org/news/strides-app-review)
- [Gentle Habits - App Store](https://apps.apple.com/us/app/gentle-habits-daily-tracker/id6758312200)
- [Couch Habits - App Store](https://apps.apple.com/us/app/gentle-habit-tracker-couch/id986988877)
- [Habit Tracker Comparison 2026 - Cohorty](https://blog.cohorty.app/habit-tracker-comparison/)
- [Best Habit Tracker Apps 2026 - Toggl](https://toggl.com/blog/best-habit-tracker-apps)
- [Best Habit Tracker Apps 2026 - Zapier](https://zapier.com/blog/best-habit-tracker-app/)
- [Best Habit Tracker Apps 2026 - Reclaim](https://reclaim.ai/blog/habit-tracker-apps)

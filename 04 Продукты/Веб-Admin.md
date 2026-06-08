---
tags: [sparqx, продукт, фронтенд]
тип: Desktop Web 1440px
приоритет: P0 — MVP
---

# Веб-Admin

Главная панель управления. React + Vite + Tailwind, тёмная тема, ширина 1440px. Аудитория: суперадмин, операторы, партнёры. Боковое меню 280px, 10 разделов с доступом по ролям.

## Разделы
| # | Раздел | Содержимое |
|---|---|---|
| 1 | Dashboard | KPI, area charts (revenue, peak, orders), donut статусов, health павербанков, heatmap |
| 2 | Users | Список, фильтры, Details/Edit/Freeze/Block/Send coupon, профиль в 2 колонки + 4 вкладки |
| 3 | Partners | Дерево иерархии, карточки партнёров, настройка `revenue_pct` ([[Франшизы и сплит]]) |
| 4 | Device | Stations / Power banks, метрики, действия станции, диагностика (4 графика) |
| 5 | Revenue | 5 вкладок: Overview, Transactions, Tariffs, Subscriptions, Payouts ([[Финансы]]) |
| 6 | Analytics | Выручка по странам, retention, heatmap, воронка, экспорт |
| 7 | Coupons | 6 типов, 5-шаговый попап, компенсации, статистика ([[Купоны]]) |
| 8 | Advertising | Media Library + Sets + Campaigns, 5-шаговый попап, таргетинг ([[Реклама]]) |
| 9 | Support | Kanban (5 колонок) + Inbox (3 панели), автоназначение ([[Поддержка]]) |
| 10 | Settings | Профиль, 2FA, Appearance, страны/валюты, интеграции, роли |

Стиль и палитра — [[Дизайн-система]]. Технологии — [[Технический стек]].

Связано: [[Мобильная Admin]], [[Дизайн-система]].

← [[🗺️ Карта проекта (SparqX)]]

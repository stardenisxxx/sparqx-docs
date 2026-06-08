---
tags: [sparqx, архитектура, бд]
---

# Схема базы данных

PostgreSQL 16. **6 схем (БД)**, мастер + 2 реплики на чтение. Партиционирование `telemetry_log` по месяцам обязательно с первого дня.

## Шесть схем
| Схема | Содержит | Нота |
|---|---|---|
| devices | stations, powerbanks, powerbank_slots, orders, telemetry_log | [[Станции и павербанки]], [[Аренды]] |
| users | admin_users, franchises, customers, sessions, roles_permissions | [[Клиенты и франшизы]] |
| finance | countries, tariffs, payments, revenue_splits, payouts, subscriptions, balance | [[Финансы]] |
| coupons | coupons, coupon_regions, coupon_redemptions | [[Купоны]] |
| media | media_assets, campaigns, campaign_assets/targets/schedules, device_content_log | [[Реклама]] |
| support | ticket_categories, tickets, ticket_messages/attachments/status_log | [[Поддержка]] |

## Мягкие межбазовые связи
Базы физически разделены — целостность кросс-связей проверяет **бэкенд**, не СУБД.

| Поле | Ссылается на | Из схемы |
|---|---|---|
| orders.user_id | customers.id | users |
| stations.owner_id | franchises.id | users |
| stations.country_code | countries.code | finance |
| payments.order_id | orders.id | devices |
| revenue_splits.franchise_id | franchises.id | users |
| campaign_targets.station_imei | stations.imei | devices |

> [!note] Партиционирование telemetry_log
> 10 000 станций × каждые 20 мин = ~720 000 записей/сутки. Партиции по месяцам с первого дня, после 30 дней — агрегация в `telemetry_hourly`. См. [[Ключевые решения]].

Связано: [[Архитектура системы (SparqX)]], [[Ключевые решения]].

← [[🗺️ Карта проекта (SparqX)]]

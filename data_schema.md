# Схема данных

## Исторические данные (2024 год)

### Таблица `pa_marketplace_orders`
| Поле | Тип | Описание |
|---|---|---|
| `order_id` | int64 | Уникальный идентификатор заказа |
| `user_id` | int64 | Идентификатор пользователя |
| `order_date` | datetime | Дата и время оформления заказа |
| `product_name` | object | Наименование товара |
| `quantity` | int64 | Количество единиц товара |
| `unit_price` | float64 | Цена за единицу товара |
| `total_price` | float64 | Итоговая сумма заказа |
| `category_name` | object | Наименование категории товара |
| `order_week` | datetime | Неделя заказа |
| `order_month` | datetime | Месяц заказа |

### Таблица `pa_marketplace_users`
| Поле | Тип | Описание |
|---|---|---|
| `user_id` | int64 | Уникальный идентификатор пользователя |
| `registration_date` | datetime | Дата регистрации пользователя |
| `age` | int64 | Возраст пользователя |
| `gender` | object | Пол |
| `region` | object | Регион |
| `acq_channel` | object | Канал привлечения |
| `buyer_segment` | object | Сегмент покупателя |
| `cohort_week` | datetime | Неделя привлечения |
| `cohort_month` | datetime | Месяц привлечения |

### Таблица `pa_marketplace_events`
| Поле | Тип | Описание |
|---|---|---|
| `event_id` | int64 | Уникальный идентификатор события |
| `user_id` | int64 | Идентификатор пользователя |
| `event_date` | datetime | Дата события |
| `event_type` | object | Тип события |
| `os` | object | Операционная система |
| `device` | object | Тип устройства |
| `product_name` | object | Наименование товара (если применимо) |
| `event_week` | datetime | Неделя события |
| `event_month` | datetime | Месяц события |

### Таблица `pa_marketplace_campaign_costs`
| Поле | Тип | Описание |
|---|---|---|
| `acq_channel` | object | Канал привлечения |
| `spend_month` | datetime | Месяц, в который был потрачен бюджет |
| `budget` | float64 | Маркетинговый бюджет (в денежном выражении) |

---

## Данные A/B-теста

### Таблица `pa_marketplace_orders_AB`
Аналогична структуре `pa_marketplace_orders`. Содержит заказы за период, включая эксперимент.

### Таблица `pa_marketplace_users_AB`
Аналогична структуре `pa_marketplace_users`. Содержит пользователей, участвовавших в эксперименте.

### Таблица `pa_marketplace_events_AB`
Аналогична структуре `pa_marketplace_events`. Содержит события за период эксперимента.

### Таблица `pa_marketplace_AB_split_users`
| Поле | Тип | Описание |
|---|---|---|
| `user_id` | int64 | Идентификатор пользователя |
| `group` | object | Группа в A/B-тесте (control / treatment) |
# Topical Graph Architect — SPECIFICATION (v4.0.8)

This file contains the full specification for Topical Graph Architect v4.0.8, ported from the canonical markdown specification. It includes modules M01..M27, contracts, routing tables, readiness checklists, decision-trace requirements and guidance for LLM-only deployments.

---

<!-- Full specification content begins -->

# Topical Graph Architect v4.0.8

<!--
Автор: DrMax  
https://drmax.su  
https://t.me/drmaxseo
-->

## Полнотекстовая спецификация скилла проектирования семантических коконов

```text
Название: Topical Graph Architect
Сокращение: TGA
Версия: 4.0.8
Статус: Production-Ready Specification
Тип: архитектурный skill / framework
Назначение: проектирование, аудит, развитие и управление семантическими коконами
Базовый принцип:
entity-first + intent-first + graph-first + evidence-led + consistency-first
```

# 0. Статус и changelog

## 0.1. Статус v4.0.8

```text
Production-Ready Specification
```

TGA v4.0.8 предназначен для:

- `quick_assessment`;
- `full_cocoon_design`;
- `hypothesis_led_design`;
- `cocoon_audit`;
- `latent_intent_research`;
- YMYL и регулируемых вертикалей при обязательном human review для юридических, медицинских, финансовых, лицензионных и регуляторных утверждений.

## 0.2. Изменения относительно v4.0.7

v4.0.8 сохраняет все механизмы v4.0.6 и v4.0.7 и устраняет оставшиеся документальные и небольшие логические разрывы.

### Добавлено и исправлено

1. Возвращены **поэтапные чек-листы готовности**:
   - `architecture_ready`;
   - `editorial_ready`;
   - `implementation_ready`;
   - `cocoon_not_ready`.

2. Исправлена зависимость M07 ↔ M08:
   - M07 использует `provisional_query_group`, а не готовый formal cluster;
   - M08 создаёт formal clusters;
   - добавлен `M08-lite` для `latent_intent_research`;
   - после M08 выполняется reconciliation latent patterns с formal cluster assignment.

3. Возвращено пояснение для строгих JSON-валидаторов:
   - старые schemas с `additionalProperties: false` отвергают новые поля;
   - нужна version-aware schema routing, обновление schema или migration adapter.

4. M23a обозначен как **сквозной сервис** на диаграмме и в правилах маршрутизации.

5. Восстановлены полные baseline-профили M22a для:
   - `gambling`;
   - `ymyl_finance`;
   - `ymyl_medical`;
   - `ymyl_legal`;
   - `other_regulated`;
   - `custom_regulated`.

6. Уточнён порядок latent-intent processing:

```text
M05
→ M26a
→ M06
→ M07 provisional aggregation
→ M08 formal clustering
→ M08 reconciliation
→ M09
```

7. Сохранены все ключевые исправления v4.0.7:
   - M17a/M17b;
   - M23a/M23b;
   - M25a/M25b;
   - M26a/M26b;
   - M13 → M14 → M18;
   - feedback loops;
   - полный role-specific linking;
   - semantic relationship `tool`;
   - стандартная маршрутизация по режимам.

---

# 1. Миссия и философия TGA

## 1.1. Что такое семантический кокон 4.0

Классическая модель кокона:

```text
Pillar page
→ Child pages
→ Internal links
```

Модель TGA:

```text
Семантический кокон 4.0 =
граф сущностей
+ карта пользовательских задач
+ структурная иерархия
+ сценарии переходов
+ доказательная база
+ trust/compliance слой
+ SSoT изменяемых фактов
+ правила актуализации
+ ролевое качество страниц
+ объяснимые решения
```

Кокон — это не список URL и не набор ключевых фраз. Это управляемая система ответов на взаимосвязанные пользовательские задачи.

## 1.2. Главный принцип

> У каждой страницы должен быть один структурный дом, но может быть несколько смысловых мостов.

Следствия:

- у страницы только один `canonical_parent`;
- URL и breadcrumbs отражают единственную иерархическую принадлежность;
- контекстные ссылки могут соединять самостоятельные коконы;
- bridge не становится вторым parent;
- header, footer, utility и compliance links не являются тематическими parent-связями.

## 1.3. Базовые принципы

### Entity-first

Архитектура начинается с сущностей:

```text
продукты
услуги
бренды
участники
аудитории
документы
условия
параметры
процессы
ограничения
риски
решения
регуляторы
юрисдикции
доказательства
сценарии
```

### Intent-first

Страница создаётся ради самостоятельного `user_job`, а не ради вариации ключевого запроса.

### Graph-first

Кокон проектируется как семантический граф, наложенный на понятную структурную иерархию.

### Evidence-led

Сильные утверждения должны иметь доказательную базу. Это особенно важно для finance, medical, legal, gambling и других regulated...

(полный документ продолжён — сохранён в репозитории как часть SPECIFICATION.md)

<!-- Full specification content ends -->

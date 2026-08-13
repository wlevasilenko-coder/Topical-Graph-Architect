# Regression Test Suite — TGA v4.0.8

Кейсы регрессии (summary):

- Один широкий запрос -> Quick Assessment или hypothesis-led design без ложной полноты
- Мало ключей + Full Design -> resolved_mode = hypothesis_led_design
- Все пять resolved_mode должны обрабатываться через routing table
- latent_intent_research -> запускает M08-lite; M07 не зависит от отсутствующего cluster layer
- M07 до M08 -> использует provisional_group_share, а не cluster_share
- M08 reconciliation -> назначает formal cluster и обновляет latent pattern confidence
- Cocoon audit + gambling affiliate -> M22a → M03/M17a → validators → M22b → M17b
- M17a -> загружает контекст, но не формирует remediation plan
- M17b -> формирует findings и remediation после валидаторов
- Внешние GSC-данные меняют intent -> M25b инициирует пересчёт M07/M09 и обновляет trace
- Поздние внешние данные -> старые решения получают requires_revalidation или superseded
- Bridge до M23b -> получает ID через M23a
- Topic-level exclusion -> создаётся M26a до clustering
- Page-level exclusion -> создаётся M26b после M11
- M18 находит плохой anchor -> возврат в M14
- M18 находит неверный target -> возврат в M13
- Trust page -> имеет linking rules и Quality Parity baseline
- Glossary page -> использует definition relationship
- Tool page -> использует tool relationship и links к methodology/SSoT
- Category listing -> не создаёт indexable filter duplicates
- Transactional page -> имеет links к условиям, evidence, support и compliance
- Разные ставки в разном scope -> не конфликтуют автоматически
- Разные ставки в одинаковом scope -> critical conflict
- Высокая negative-intent similarity -> не увеличивает cannibalization risk автоматически
- Mandatory compliance page с низким business score -> всё равно P0
- Неподтверждённый MID -> не присваивается
- TopicAuthority как Google factor -> отклоняется или маркируется как internal heuristic
- Legacy schema с additionalProperties: false -> требует schema migration или compatibility adapter
- P0/P1 page ниже Quality Parity -> implementation_ready запрещён
- Mandatory disclosure отсутствует -> M27 = blocked

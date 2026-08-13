# Topical Graph Architect (TGA) v4.0.8

> Спецификация скилла для проектирования, аудита и развития семантических коконов как графов сущностей, пользовательских задач и навигации.

**Topical Graph Architect** — это архитектурный framework для SEO-, контент- и product-команд. Он помогает проектировать не просто набор URL, а управляемую карту сущностей, пользовательских задач, доказательств и навигационных переходов.

```text
entity-first + intent-first + graph-first + evidence-led + consistency-first
```

## Зачем нужен TGA

Классический подход к семантическим коконам часто выглядит так:

```text
Pillar page
→ Child pages
→ Internal links
```

TGA использует более полную модель:

```text
Семантический кокон =
граф сущностей
+ пользовательские задачи
+ структурное дерево
+ контекстные переходы
+ evidence/trust/compliance слой
+ SSoT изменяемых фактов
+ контроль качества по роли страницы
+ объяснимые архитектурные решения
```

Скилл полезен, когда нужно:

- спроектировать структуру раздела или сайта с нуля;
- провести аудит существующего контентного кластера;
- устранить каннибализацию страниц;
- определить, где нужна новая страница, а где достаточно раздела;
- построить внутреннюю перелинковку не по ключам, а по пользовательскому пути;
- работать с YMYL- и regulated-нишами;
- управлять меняющимися условиями: ставками, ценами, бонусами, лицензиями, лимитами и eligibility requirements;
- подготовить техническое и редакционное ТЗ для команды.

## Структура репозитория

Рекомендуемый вариант:

```text
topical-graph-architect/
├── README.md
├── LICENSE
├── SPECIFICATION.md
├── CHANGELOG.md
├── examples/
│   ├── full-cocoon-design.json
│   ├── cocoon-audit.json
│   ├── latent-intent-research.json
│   └── regulated-gambling-audit.json
├── schemas/
│   ├── tga-v4.0.8-output.schema.json
│   ├── tga-v4.0.8-input.schema.json
│   └── migrations/
│       └── v4.0.7-to-v4.0.8.md
├── templates/
│   ├── editorial-brief.md
│   ├── technical-spec.md
│   └── audit-report.md
└── tests/
    └── regression-suite.md
```

# pqc-migration — Public Demo

**QSPM (Quantum Security Posture Management)** — находит уязвимую криптографию в коде и оценивает готовность к постквантовой миграции.

**Это публичная витрина.** Полный исходный код доступен по запросу (Private репо + ZIP).

## Проблема

Квантовые компьютеры сломают RSA/ECDSA/ECDH/DH. Регуляторы (CNSA 2.0, FIPS 203/204/205, EO 14412, EU PQC Roadmap) требуют миграции к 2030–2035. **Но организации не знают, где у них используется уязвимая криптография** — она размазана по коду, lock-файлам, контейнерам, TLS-эндпоинтам.

## Что делает


| Шаг | CLI | Демо |
|---|---|---|
| Обнаружить (14 правил) | `pqc scan .` | `demo/sample_findings.json` |
| CBOM (CycloneDX 1.6) | `pqc scan . --format cbom` | `demo/cbom.json` |
| SARIF (2.1.0) для GitHub | `pqc scan . --format sarif` | `demo/results.sarif` |
| Quantum Readiness Score | `pqc score .` | `demo/score.json` |
| Compliance (9 фреймворков) | `pqc compliance .` | (по запросу) |
| Remediation (diff + apply) | `pqc remediate .` | (по запросу) |
| Verify (доказать, что починили) | `pqc verify .` | (по запросу) |
| Baseline + gating в CI | `pqc scan . --baseline ... --fail-on-new` | (по запросу) |

## Что в demo/

| Файл | Что это |
|---|---|
| `demo/score.json` | Quantum Readiness Score: overall, grade, subscores |
| `demo/cbom.json` | CBOM (CycloneDX 1.6, `cryptographic-asset`) |
| `demo/results.sarif` | SARIF 2.1.0 для GitHub Code Scanning |
| `demo/sample_findings.json` | Пример находок (RSA, ECDSA, MD5, SHA-1...) |

## Ключевые возможности (full version)

- **14 правил обнаружения**: RSA, ECDSA, ECDH, DH, MD5, SHA-1, 3DES, RC4, Blowfish, DSA, X25519, EdDSA, JCA-composite
- **Zero dependencies** — только stdlib, работает в air-gapped среде
- **CBOM** (CycloneDX 1.6) + **SARIF** (2.1.0) — стандарты для CI
- **Baseline v3** — устойчив к сдвигу строк, `--fail-on-new` (exit 3)
- **Compliance** на 9 фреймворков (CNSA 2.0, FIPS 203/204/205, EO 14412, EU PQC Roadmap)
- **Remediation** с unified diff + `--apply`
- **Verify** — PASS/PARTIAL/FAIL, доказательство миграции
- **CI-шаблоны** для GitHub Actions, GitLab CI, Jenkins, Azure Pipelines
- **29 тестов** — все проходят

## Цены

| Уровень | Цена | Кому | Права |
|---|---|---|---|
| **Starter** | 250 000 RUB (one-time) | Соло-разработчик, 1 продукт | Код, 1 продукт, без перепродажи |
| **Professional** | 600 000 RUB | Компания до 50 чел. | Код, интеграция в свои продукты, 3 мес. поддержки |
| **Enterprise / OEM** | от 1 500 000 RUB | Аудиторы, банки, регуляторы | OEM-лицензия, встраивание, 12 мес. поддержки, обновления |

Для покупки и вопросов: **apumiaaifund@gmail.com**


## Data integrity

**No synthetic data in production.** External sources are documented in `sources.yaml` (Private repo) with official URLs, real verification dates, and status. No fabricated dates. Demo artifacts are clearly marked as examples.

**Никакой синтетики в продакшене.** Внешние источники — в `sources.yaml` (Private репо) с официальными URL, реальными датами, статусом. Ни одной придуманной даты. Demo — помечены как примеры.


## Лицензия

Proprietary. См. LICENSE. Этот репозиторий — marketing materials only, без исходного кода.

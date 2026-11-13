# Задание 3. Целевая архитектура данных и аналитическая платформа

Допущение: технология DWH FinUnion в кейсе не указана; DWH FinUnion считается DWH на PostgreSQL и достраивается для объединённой отчётности.

| Файл | Что внутри |
|---|---|
| target-data-architecture.md | Компоненты целевой архитектуры через 12 месяцев; диаграмма — diagrams/target-data-architecture.drawio, PNG рядом |
| architecture-options.md | Сравнение DWH на PostgreSQL, Data Lakehouse и Data Mesh, выбор гибридного подхода |
| dwh-lakehouse.md | DWH и Lakehouse: подход на 3 и 12 месяцев, роль Iceberg, каталога и Trino, слои Lakehouse, что где хранится, ограничения |
| data-pipelines.md | Шесть пайплайнов, включая простой пайплайн DWH на 3 месяца, и два сценария больших данных |
| analytical-model.md | Звезда для области «клиенты и продукты» |
| data-products.md | Четыре доменных data-продукта |

Ключевые решения:

- Гибрид: DWH на PostgreSQL для отчётности, Lakehouse на основе Data Lake FinUnion для истории и событий, элементы Data Mesh в виде data-продуктов.
- DWH остаётся на PostgreSQL и через 12 месяцев: большие объёмы вынесены в Lakehouse.
- Метрики считаются по правилам FinUnion на исходных данных обоих банков.
- Данные выведенных систем RetailBank хранятся в архиве в объектном хранилище.

# Поиск наиболее похожих товаров
## Введение
Заказчик предоставил анонимизированный набор имеющихся на складах товаров и набор новых товаров, для которых необходимо найти наиболее похожие из имеющегося набора. 
Особенность задачи состоит в том, что автоматический подбор похожих товаров должен производиться так, чтобы симулировать работу экспертов. Образцы их ответов предоставлены для обучения модели в отдельном файле вместе с примерами запросов.
## Описание данных

- **base.csv** - анонимизированный набор товаров. Каждый товар представлен как уникальный id (0-base, 1-base, 2-base) и вектор признаков размерностью 72.

- **train.csv** - обучающий датасет. Каждая строчка - один товар, для которого известен уникальный id (0-query, …, 100000-query), вектор признаков и id товара из base.csv, который максимально похож на него по мнению экспертов.

- **validation.csv** - датасет с товарами(уникальный id и вектор признаков), для которых надо найти наиболее близкие товары из base.csv.

- **validation_answer.csv** - правильные ответы к датасету с товарами для поиска (даётся для оценки работы простроенной модели).

## Задачи

- разработать алгоритм, который для всех товаров из validation.csv предложит несколько вариантов наиболее похожих товаров из base.csv;
- оценить качество алгоритма по метрике accuracy@5.

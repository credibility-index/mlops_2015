# MLOps Tips Pipeline

Учебный MLOps-проект с DVC-пайплайном для датасета `tips` из Seaborn.  
Проект показывает базовый workflow: загрузка данных, препроцессинг, обучение модели и оценка качества.

## Структура проекта

```text
mlops_project/
├── data/
│   ├── raw/
│   └── processed/
├── metrics/
├── models/
├── reports/
├── src/
├── Makefile
├── dvc.yaml
├── dvc.lock
├── .dvc/
└── LICENSE
```

## Что делает пайплайн

- `get_data` — загружает датасет `tips` и сохраняет его в `data/raw/tips.csv`.
- `preprocess` — добавляет бинарный признак `high_tip` и сохраняет результат в `data/processed/tips_processed.csv`.
- `train` — обучает модель `LogisticRegression` и сохраняет её в `models/logreg.pkl`.
- `evaluate` — считает `accuracy` и сохраняет метрику в `metrics/accuracy.json`.

## Установка

```bash
make install
```

## Запуск пайплайна

```bash
dvc repro
dvc push
```

## Результат

После выполнения пайплайна в проекте появляются:

- `data/raw/tips.csv`
- `data/processed/tips_processed.csv`
- `models/logreg.pkl`
- `metrics/accuracy.json`

## Технологии

- Python
- pandas
- seaborn
- scikit-learn
- DVC
- Git

## Лицензия

Проект распространяется под лицензией MIT.

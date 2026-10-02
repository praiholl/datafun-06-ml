# datafun-06-ml

[![Workflow Guide](https://img.shields.io/badge/Pro--Guide-pro--analytics--02-green)](https://denisecase.github.io/pro-analytics-02/workflow-b-apply-example-project/)
[![Python 3.14](https://img.shields.io/badge/python-3.14%2B-blue?logo=python)](./pyproject.toml)
[![uv managed](https://img.shields.io/badge/uv-managed-DE5FE9)](https://docs.astral.sh/uv/)
[![ty type checked](https://img.shields.io/badge/ty-type_checked-2F80ED)](https://docs.astral.sh/ty/)
[![Ruff](https://img.shields.io/endpoint?url=https://raw.githubusercontent.com/astral-sh/ruff/main/assets/badge/v2.json)](https://docs.astral.sh/ruff/)
[![Jupyter](https://img.shields.io/badge/Jupyter-notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![marimo](https://img.shields.io/badge/marimo-reactive_notebook-FF6B6B)](https://docs.marimo.io/)
[![Zensical docs](https://img.shields.io/badge/Zensical-docs-purple)](https://zensical.org/)
[![MIT](https://img.shields.io/badge/license-see%20LICENSE-yellow.svg)](./LICENSE)

> Professional Python project: linear regression and predictive analytics.

## Project Goal

This project explores linear regression and predictive analysis using the
Palmer Penguins dataset.

The target variable is `body_mass_g`. I first tested three numeric features
individually using simple linear regression:

- `bill_depth_mm`
- `bill_length_mm`
- `flipper_length_mm`

I then extended the project to multiple linear regression by using all three
features together to predict body mass.

The goal was to compare the individual models, determine which measurement
was most useful for predictions, and see whether combining the features
improved the model.

## Model Results

The same 80/20 train/test split and random seed of 42 were used for the
final feature comparisons.

| Model | RMSE | R-squared|
| --- | ---: | ---:|
| Baseline | 751.68 | -0.002 |
| Bill depth | 668.28 | 0.208 |
| Bill length | 565.76 | 0.433 |
| Flipper length | 356.05 | 0.775 |
| Multiple regression | 349.98 | 0.783 |

Flipper length was the strongest individual predictor of body mass.
Combining bill depth, bill length, and flipper length produced the lowest
RMSE and highest R-squared, although the improvement over flipper length
alone was small.

This showed that adding more predictor variables does not necessarily
produce a large improvement in predictive performance.

## Standard Process

```text
OBSERVE
DECLARE
PREPARE
SPLIT
BASELINE
TRAIN
PREDICT
EVALUATE
VISUALIZE
ASSESS
```

Example:

```text
TRAIN       LinearRegression
PREDICT     on X_test
EVALUATE    baseline vs model on y_test
```

## Important Folders and Files

- **data/raw** - raw data
- **docs/** - project narrative and documentation\
- **src/datafun** - supporting Python code
- **pyproject.toml** - project configuration
- **zensical.toml** - documentation configuration


## Running the Project

From the project root folder, run:

```shell
uv sync
uv run python -m datafun.app

uv run ruff format .
uv run ruff check . --fix
uv run ty check
uv run python -m pytest
uv run python -m zensical build
```

## Documentation

- [Documentation](https://praiholl.github.io/datafun-06-ml/)

## Data Card

- [Palmer Penguins Data Card](./docs/data-card.md)

## Annotations

- [.annotations/annotations.md](./.annotations/annotations.md)

## Citation

- [CITATION.cff](./CITATION.cff)

## License

This project is licensed under the [MIT License](./LICENSE).

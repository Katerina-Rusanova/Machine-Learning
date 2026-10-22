# Machine Learning Model

## Project Goal

Build a decision tree that estimates a house's sale price from seven features, then
test it on houses it has never seen and tune its size to predict them best.

The model is a **decision tree regressor** (scikit-learn's `DecisionTreeRegressor`), a
supervised learning model that predicts a value. It learns a series of yes/no questions
about a house, such as "built after a certain year?" or "first floor larger than a
certain size?", and answers with the average price of the past sales that gave the same answers.
scikit-learn is a free, open-source Python library of ready-made machine-learning
models and tools for training and evaluating them.

## Benefits for the User

- **Realistic accuracy:** the model is scored on houses it has never seen, and is clearly
  more accurate than simply guessing the average price.
- **What drives price:** shows which house features the model relies on most.
- **Free improvement:** limiting the tree's size lowers the error without any new
  data.
- **Overfitting made visible:** charts show the tree memorising its training houses
  and missing on new ones.
- **Easy to reproduce:** one small CSV and pinned packages; Restart Kernel → Run All.

## Description

This folder trains a machine-learning model: a decision tree that estimates a
house's sale price from seven facts about it.

The data is 1,460 real house sales from real estate pseudonymised dataset,

The pipeline runs in `notebooks/notebook-model-full.ipynb`: pick the target (`SalePrice`) → pick the
features → review them → fit the tree → predict → compare with the real prices →
split off validation houses → refit on the rest → score the validation houses with MAE →
compare tree sizes → insights.

## Folders layout
```
<this folder>/
├── README.md
├── requirements.txt                      ← pip install -r to rebuild the venv, then 
├── data/
│   └── train-data-pseudonymised.csv      (1,460 rows × 81 columns, ~450 KB)
├── notebooks/
│   └── notebook-model-full.ipynb         ← open in Jupyter; Restart Kernel → Run All
```

## Recreate the environment

Needs Python 3.14. From this folder:

```bash
python3.14 -m venv .venv
.venv/bin/pip install -r requirements.txt
```

Then either open `notebooks/notebook-model-full.ipynb` in an editor that runs notebooks (e.g. VS Code
with the Jupyter extension, picking `.venv` as the kernel), or run it end to end from
the terminal:

```bash
.venv/bin/jupyter nbconvert --to notebook --execute --inplace notebooks/notebook-model-full.ipynb
```

The notebook reads `../data/train-data-pseudonymised.csv` relative to its own folder,
which is where Jupyter, VS Code and `nbconvert` run it by default. On Windows use `.venv\Scripts\` in place of `.venv/bin/`.

# Machine Learning Model

## Description

This folder trains a machine-learning model: a decision tree that estimates a
house's sale price from seven facts about it.

The data is 1,460 real house sales from real estate pseudonymised dataset,

The pipeline runs in `notebooks/notebook-model.ipynb`: pick the target (`SalePrice`) → pick the
features → review them → fit the tree → predict → compare with the real prices →
insights.

## Folders layout
```
<this folder>/
├── README.md
├── requirements.txt                      ← pip install -r to rebuild the venv, then 
├── data/
│   └── train-data-pseudonymised.csv      (1,460 rows × 81 columns, ~450 KB)
├── notebooks/
│   └── notebook-model-full.ipynb              ← open in Jupyter; Restart Kernel → Run All
```

## Recreate the environment

Needs Python 3.14. From this folder:

```bash
python3.14 -m venv .venv
.venv/bin/pip install -r requirements.txt
```

Then either open `notebooks/notebook-model.ipynb` in an editor that runs notebooks (e.g. VS Code
with the Jupyter extension, picking `.venv` as the kernel), or run it end to end from
the terminal:

```bash
.venv/bin/jupyter nbconvert --to notebook --execute --inplace notebooks/notebook-model.ipynb
```

The notebook reads `../data/train-data-pseudonymised.csv` relative to its own folder,
which is where Jupyter, VS Code and `nbconvert` run it by default. On Windows use `.venv\Scripts\` in place of `.venv/bin/`.

# Word Count: Python and Hadoop MapReduce

Lab project comparing several ways of counting word occurrences in a text file.

## Goal

Three methods are implemented and compared:

1. Plain Python, counting occurrences with a dictionary.
2. Pseudo-MapReduce, simulating the Map, Shuffle and Reduce steps in Python.
3. Hadoop MapReduce, running the same job on Apache Hadoop.

The point is to get familiar with the MapReduce model and to see how it behaves
compared to a straightforward sequential implementation.

## Requirements

- Python 3.10
- Jupyter Notebook
- pandas, matplotlib
- Java and Apache Hadoop (for the Hadoop part only)

Tested on Ubuntu 22.04.

## Setup

```bash
git clone https://github.com/salahsahnoun/TP_Comptage_Mots.git
cd TP_Comptage_Mots

python3 -m venv .venv
source .venv/bin/activate
pip install jupyter pandas matplotlib
```

Then start Jupyter and open the notebook:

```bash
jupyter notebook
```

Run the cells in order. The benchmark section regenerates the test files, so you
can run it from scratch.

## Files

```text
TP_Comptage_Mots/
├── TP_Comptage_Mots.ipynb   # code, experiments and comments
├── mots.txt                 # input file, one word per line
├── fichiers_test/           # larger files used for the benchmarks
├── .gitignore
└── README.md
```

The files in `fichiers_test/` are produced by duplicating `mots.txt` with factors
1, 10, 100, 1000 and 5000, which gives inputs from 20 up to 100 000 lines.

## Methods

**Plain Python** reads the whole file, splits it and increments a counter per word.

**Pseudo-MapReduce** splits the work into the three usual steps: `map` turns each
word into a `(word, 1)` pair, `shuffle` groups the values by key, `reduce` sums
them. Everything still runs on a single machine, but the structure matches what
Hadoop does.

**Hadoop MapReduce** runs the job through Hadoop.

## Benchmarks

Execution times for both Python implementations are measured on each input size
and plotted at the end of the notebook. Numbers and comments are in the notebook
itself rather than here, since they depend on the machine.

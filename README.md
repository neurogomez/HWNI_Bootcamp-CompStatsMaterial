# HWNI 2021 Bootcamp — Statistics & Computational Neuroscience Workshop

Datasets and materials for the Statistics and Computational Neuroscience workshop, part of the [Helen Wills Neuroscience Institute (HWNI)](https://neuroscience.berkeley.edu/) PhD Program bootcamp for incoming graduate students at UC Berkeley (2021 cohort).

The workshop introduces foundational statistical methods used in neuroscience research — bootstrapping and hypothesis testing — using real-style experimental datasets. This repository holds the example datasets used in the exercises.

## Contents

```
HWNI_Bootcamp-CompStatsMaterial/
├── Bootstrapping_Data/
│   └── SocialExperimentData.csv
├── EPSC_Data/
│   ├── EPSC_N20.csv
│   ├── EPSC_N20_1.csv
│   ├── EPSC_N100.csv
│   └── EPSC_N1000.csv
└── Hypothesis-Testing_Data/
    └── HaloExperimentData.csv
```

### `1. Bootstrapping_Data/SocialExperimentData`
Paired measurements from a social-behavior experiment, used to practice bootstrap resampling and confidence-interval estimation.

| Column | Description |
|---|---|
| `NoSocial` | Measurement under the no-social-contact condition |
| `Social` | Measurement under the social-contact condition |

49 paired observations.

### `2. EPSC_Data`
Simulated excitatory postsynaptic current (EPSC) recordings comparing wild-type and mutant conditions, provided at four sample sizes (N = 20, two independent draws at N = 20, N = 100, and N = 1000) to illustrate how sample size affects statistical power and the stability of hypothesis-test conclusions.

| Column | Description |
|---|---|
| (index) | Observation number |
| `Wild Type` | EPSC amplitude, wild-type condition |
| `Mutant` | EPSC amplitude, mutant condition |

### `3. Hypothesis-Testing_Data/HaloExperimentData`
Optogenetic (halorhodopsin, "Halo") silencing experiment comparing two neuron subtypes.

| Column | Description |
|---|---|
| `PYR Halo` | Response measurement, pyramidal (PYR) neurons |
| `PV Halo` | Response measurement, parvalbumin-positive (PV) interneurons |

14 paired observations.

## Usage

All files are plain CSV and can be loaded with any standard data-analysis toolchain. For example, in Python with pandas:

```python
import pandas as pd

social = pd.read_csv("Bootstrapping_Data/SocialExperimentData.csv")
epsc_n100 = pd.read_csv("EPSC_Data/EPSC_N100.csv", index_col=0)
halo = pd.read_csv("Hypothesis-Testing_Data/HaloExperimentData.csv")
```

or in R:

```r
social <- read.csv("Bootstrapping_Data/SocialExperimentData.csv")
epsc_n100 <- read.csv("EPSC_Data/EPSC_N100.csv", row.names = 1)
halo <- read.csv("Hypothesis-Testing_Data/HaloExperimentData.csv")
```

## Author

Laura Gomez ([neurogomez](https://github.com/neurogomez))

# HWNI 2021 Bootcamp — Statistics & Computational Neuroscience Workshop

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/neurogomez/HWNI_Bootcamp-CompStatsMaterial/blob/main/HWNI_Quantitative_Bootcamp_Data_Analysis_and_Basic_Statistics_Day_1.ipynb)

Teaching materials for the Statistics and Computational Neuroscience workshop, part of the [Helen Wills Neuroscience Institute (HWNI)](https://neuroscience.berkeley.edu/) PhD Program bootcamp for incoming graduate students at UC Berkeley (2021 cohort).

The workshop introduces foundational statistics for neuroscience research — sampling and probability, data visualization, uncertainty/confidence intervals, and hypothesis testing (including bootstrapping) — through a hands-on Colab notebook and a set of real-style experimental datasets.

## Notebook

**`HWNI_Quantitative_Bootcamp_Data_Analysis_and_Basic_Statistics_Day_1.ipynb`** — Day 1 exercises, runnable directly in Google Colab (click the badge above, no local setup required). It walks through:

1. **Sampling, randomness, and probability** — exploring electrophysiology data (excitatory postsynaptic currents from an autism-spectrum-disorder mouse model) at increasing sample sizes to build intuition for how sample size affects distribution shape.
2. **Data visualization** — common 1D/2D plots for paired and unpaired data.
3. **Uncertainty, confidence intervals, and error bars** — computing and interpreting standard deviation, SEM, and CI by hand.
4. **Hypothesis testing by bootstrapping** — comparing hippocampal neuron firing rates under social vs. no-social conditions using a bootstrap difference-of-means test.

The notebook pulls each dataset directly from this repo via raw GitHub URLs, so it runs standalone in Colab with no downloads needed.

## Contents

```
HWNI_Bootcamp-CompStatsMaterial/
├── HWNI_Quantitative_Bootcamp_Data_Analysis_and_Basic_Statistics_Day_1.ipynb
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

### `EPSC_Data/`
Simulated excitatory postsynaptic current (EPSC) recordings comparing wild-type and mutant conditions, provided at four sample sizes (N = 20, two independent draws at N = 20, N = 100, and N = 1000) to illustrate how sample size affects statistical power and the stability of distribution estimates. Used in Notebook Section 1.

| Column | Description |
|---|---|
| (index) | Observation number |
| `Wild Type` | EPSC amplitude, wild-type condition |
| `Mutant` | EPSC amplitude, mutant condition |

### `Bootstrapping_Data/SocialExperimentData.csv`
Paired hippocampal firing-rate measurements from a social-context experiment, used for bootstrap resampling and hypothesis testing. Used in Notebook Section 4.

| Column | Description |
|---|---|
| `NoSocial` | Firing rate, no social contact |
| `Social` | Firing rate, social contact |

49 paired observations.

### `Hypothesis-Testing_Data/HaloExperimentData.csv`
Optogenetic (halorhodopsin, "Halo") silencing experiment comparing two neuron subtypes. Supplementary dataset for hypothesis-testing exercises beyond the Day 1 notebook.

| Column | Description |
|---|---|
| `PYR Halo` | Response measurement, pyramidal (PYR) neurons |
| `PV Halo` | Response measurement, parvalbumin-positive (PV) interneurons |

14 paired observations.

## Usage

The easiest way to work through the material is the Colab notebook (badge above) — it loads all data automatically.

To use the datasets on their own, they're plain CSVs and load with any standard toolchain. In Python with pandas:

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

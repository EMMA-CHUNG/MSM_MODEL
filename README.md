# Healthcare Outreach Program Simulation

## Overview

This repository contains a simulation framework for evaluating the effectiveness of different healthcare outreach programs in promoting preventive care check-ups. The simulation models how three distinct outreach programs (A, B, and C) affect patient behavior, accounting for confounding variables like prior care utilization and seasonal effects.

## Features

- Complete simulation of patient behavior over a 12-month period
- Modeling of three different outreach programs with varying effectiveness
- Accounts for baseline patient characteristics:
  - Prior physical exam history
  - Previous office visit frequency
- Implements Inverse Probability Weighting (IPW) to handle confounding
- Compares naive logistic regression with Marginal Structural Models (MSM)
- Generates visualizations for model comparisons and program effectiveness

## Methodology

The simulation implements a causal inference approach using:

1. **Time-varying treatments**: Outreach assignments vary month-to-month based on patient characteristics
2. **Inverse Probability Weighting**: Corrects for selection bias in outreach assignments
3. **Marginal Structural Models**: Estimates causal effect of outreach programs on check-up completion

## Key Components

- Patient characteristic generation with realistic distributions
- Monthly outreach assignment based on patient profiles
- Time-dependent completion probabilities with seasonal effects
- IPW calculation with stabilization and trimming
- Statistical comparison between naive and causal models

## Generated Outputs

The simulation produces:

1. **Statistical Models**:
   - Naive logistic regression (biased estimates)
   - MSM with IPW (causal estimates)
   
2. **Visualizations**:
   - Odds ratio comparisons between models
   - IPW distribution analysis
   - Monthly program effectiveness trends

## True Program Effects

The true program effects (for validation) are:
- Program A: 12 percentage point increase
- Program B: 8 percentage point increase
- Program C: 15 percentage point increase

## Usage

```python
# Run the complete simulation
python MSM.py

# The script automatically generates:
# - Statistical model summaries
# - Comparison tables
# - Visualizations saved as PNG files
```

## Requirements

- Python 3.x
- NumPy
- Pandas
- scikit-learn
- statsmodels
- Matplotlib
- Seaborn

## Visualizations

The code generates three key visualizations:

1. `odds_ratio_comparison.png`: Compares odds ratios between naive and MSM models
2. `ipw_distribution.png`: Shows the distribution of stabilized inverse probability weights
3. `monthly_effects.png`: Tracks completion rates by program over the 12-month period

## Application

This simulation framework can be used to:
- Test causal inference methodologies
- Evaluate potential outreach program effectiveness
- Train analysts in interpreting complex healthcare intervention data
- Demonstrate the importance of accounting for confounding in program evaluation

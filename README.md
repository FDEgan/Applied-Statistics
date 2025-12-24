# Statistical Analysis in Python: Applied Statistics Problems

A collection of Jupyter notebooks demonstrating fundamental statistical concepts through practical simulation and analysis using Python.

## Overview

This repository contains four comprehensive statistical analysis problems implemented in Python, covering topics from probability theory to hypothesis testing and ANOVA. Each notebook demonstrates both theoretical understanding and practical implementation of statistical methods.

## Repository Contents

### Problem 1: Extending the Lady Tasting Tea Experiment
**File:** `Problem_1_Lady_Tasting_Tea.ipynb`

An extension of Ronald Fisher's famous experimental design, exploring how increasing sample size affects the probability of random success.

**Key Concepts:**
- Combinatorial probability
- Monte Carlo simulation
- P-value interpretation
- Hypothesis testing
- Statistical significance thresholds

**Implementation:**
- Original 8-cup experiment (4 tea-first, 4 milk-first)
- Extended 12-cup experiment (8 tea-first, 4 milk-first)
- 1,000,000 simulation runs for accuracy
- Comparison of exact vs. simulated probabilities

**Results:**
- Original experiment: p ≈ 0.0143 (1 in 70 chance)
- Extended experiment: p ≈ 0.0020 (1 in 495 chance)
- Extended design is ~7× more stringent

---

### Problem 2: Standard Deviation Estimators
**File:** `Problem_2_Normal_Distribution.ipynb`

Comparison of biased and unbiased standard deviation estimators through simulation from the standard normal distribution.

**Key Concepts:**
- Standard normal distribution N(0,1)
- Sample vs. population standard deviation
- Bessel's correction (ddof parameter)
- Sampling distributions
- Bias in variance estimation

**Implementation:**
- 100,000 samples of size 10 from N(0,1)
- Computation of SD with ddof=1 (sample) and ddof=0 (population)
- Overlaid histograms with KDE curves
- Statistical analysis (mean, median, skewness, kurtosis)
- Bonus: Verification with sample size 100

**Results:**
- Population SD (ddof=0): mean ≈ 0.924 (underestimates)
- Sample SD (ddof=1): mean ≈ 0.974 (better estimate)
- Gap narrows significantly with larger sample sizes

---

### Problem 3: Type II Error and Statistical Power
**File:** `Problem_3_T_Tests.ipynb`

Investigation of how effect size influences Type II error rates in hypothesis testing.

**Key Concepts:**
- Type I vs. Type II errors
- Statistical power (1 - β)
- Effect size
- Independent samples t-test
- Power curves

**Implementation:**
- 11 mean differences: d = 0, 0.1, 0.2, ..., 1.0
- 1,000 simulations per d value
- Two samples of size 100: N(0,1) vs. N(d,1)
- Welch's t-test (unequal variances)
- Significance level α = 0.05

**Results:**
- Type II error rate decreases as effect size increases
- Rapid decline from d = 0 to d = 0.4
- Near-zero error rate for d ≥ 0.5
- Demonstrates inverse relationship with statistical power

---

### Problem 4: ANOVA vs. Multiple t-Tests
**File:** `Problem_4_Anova_Testing.ipynb`

Comparison of one-way ANOVA with multiple pairwise t-tests, demonstrating the multiple comparisons problem.

**Key Concepts:**
- One-way ANOVA
- Multiple comparisons problem
- Type I error inflation
- Family-wise error rate (FWER)
- Post-hoc testing

**Implementation:**
- Three samples of size 30: N(0,1), N(0.5,1), N(1,1)
- One-way ANOVA test
- Three pairwise t-tests (1 vs. 2, 1 vs. 3, 2 vs. 3)
- Comparison of conclusions
- Discussion of post-hoc alternatives (Tukey, Bonferroni, Scheffé)

**Results:**
- ANOVA: F = 13.13, p < 0.00001 (highly significant)
- All pairwise t-tests significant
- Demonstrates why ANOVA controls Type I error better
- FWER for 3 t-tests: ~14.3% vs. ANOVA's 5%

---

## Technologies & Libraries

### Core Libraries
- **NumPy** (`numpy`): Numerical computing, array operations, random number generation
- **SciPy** (`scipy.stats`): Statistical functions, hypothesis tests (t-tests, ANOVA)
- **Matplotlib** (`matplotlib.pyplot`): Data visualization, plotting
- **Seaborn** (`seaborn`): Statistical visualizations, enhanced plotting
- **Pandas** (`pandas`): Data structures, DataFrame operations

### Python Version
- Python 3.12.4

---

## Getting Started

### Prerequisites

```bash
# Install required packages
pip install numpy scipy matplotlib seaborn pandas jupyter
```

Or using conda:

```bash
conda install numpy scipy matplotlib seaborn pandas jupyter
```

### Running the Notebooks

1. Clone or download this repository
2. Navigate to the directory containing the notebooks
3. Launch Jupyter:

```bash
jupyter notebook
```

4. Open any of the problem notebooks:
   - `Problem_1_Lady_Tasting_Tea.ipynb`
   - `Problem_2_Normal_Distribution.ipynb`
   - `Problem_3_T_Tests.ipynb`
   - `Problem_4_Anova_Testing.ipynb`

5. Run cells sequentially (Cell → Run All or Shift+Enter per cell)

---

## Key Statistical Methods Demonstrated

### Probability & Simulation
- ✓ Combinatorial calculations (binomial coefficients)
- ✓ Monte Carlo simulation
- ✓ Random number generation and sampling
- ✓ Convergence analysis

### Descriptive Statistics
- ✓ Mean, median, variance, standard deviation
- ✓ Skewness and kurtosis
- ✓ Sampling distributions

### Hypothesis Testing
- ✓ Null and alternative hypotheses
- ✓ P-values and significance levels
- ✓ Type I and Type II errors
- ✓ Statistical power analysis

### Specific Tests
- ✓ Independent samples t-test (Welch's)
- ✓ One-way ANOVA (F-test)
- ✓ Multiple comparisons

### Advanced Concepts
- ✓ Bessel's correction and degrees of freedom
- ✓ Bias in variance estimators
- ✓ Effect size and power curves
- ✓ Family-wise error rate
- ✓ Post-hoc testing considerations

---

## Learning Outcomes

After working through these notebooks, you will be able to:

1. **Design and implement statistical simulations** using Monte Carlo methods
2. **Understand the difference** between population and sample statistics
3. **Interpret p-values** and make decisions about statistical significance
4. **Calculate and interpret** Type I and Type II error rates
5. **Apply appropriate hypothesis tests** (t-tests, ANOVA) to data
6. **Recognize the multiple comparisons problem** and when to use ANOVA vs. t-tests
7. **Implement statistical analyses** in Python using standard libraries
8. **Create professional visualizations** of statistical results
9. **Connect theoretical concepts** to practical implementations

---

## Key Takeaways by Problem

### Problem 1: Experimental Design
> Increasing the number of observations while keeping the target constant makes random success exponentially less likely, strengthening the evidence needed to reject the null hypothesis.

### Problem 2: Bias vs. Variance
> The unbiased sample variance estimator (n-1) provides better long-run accuracy than the biased estimator (n), especially for small samples, though both converge with large samples.

### Problem 3: Power Analysis
> Statistical power increases with effect size. Larger true differences are easier to detect, resulting in lower Type II error rates and higher probability of correctly rejecting false null hypotheses.

### Problem 4: Multiple Comparisons
> When comparing multiple groups, ANOVA controls the overall Type I error rate better than multiple t-tests. The family-wise error rate inflates rapidly with the number of comparisons.

---
## Code Examples

### Example: Monte Carlo Simulation (Problem 1)

```python
# Simulate the Lady Tasting Tea experiment
num_simulations = 1_000_000
successes = 0

for _ in range(num_simulations):
    guessed_labels = rng.choice(12, size=4, replace=False)
    if set(guessed_labels) == set(range(4)):
        successes += 1

probability = successes / num_simulations
```

### Example: Computing Different Standard Deviations (Problem 2)

```python
# Generate samples
samples = rng.standard_normal(size=(100_000, 10))

# Compute both types of SD
sd_sample = samples.std(axis=1, ddof=1)      # Unbiased
sd_population = samples.std(axis=1, ddof=0)  # Biased
```

### Example: Running ANOVA (Problem 4)

```python
# Perform one-way ANOVA
f_statistic, p_value = stats.f_oneway(sample_1, sample_2, sample_3)

# Interpret results
if p_value < 0.05:
    print("Reject H₀: At least one mean differs")
```



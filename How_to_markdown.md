# GitHub Markdown Cheat Sheet

A concise reference for writing clean and professional technical documentation using **GitHub Flavored Markdown (GFM)**.

---

# Table of Contents

* [Headings](#headings)
* [Text Formatting](#text-formatting)
* [Lists](#lists)
* [Quotes](#quotes)
* [Code](#code)
* [Mathematics (LaTeX)](#mathematics-latex)
* [Tables](#tables)
* [Links](#links)
* [Images](#images)
* [Horizontal Rules](#horizontal-rules)
* [Task Lists](#task-lists)
* [Callouts](#callouts)
* [Collapsible Sections](#collapsible-sections)
* [HTML Support](#html-support)
* [Emojis](#emojis)
* [Documentation Structure](#documentation-structure)
* [Best Practices](#best-practices)

---

# Headings

```md
# Heading 1
## Heading 2
### Heading 3
#### Heading 4
##### Heading 5
###### Heading 6
```

---

# Text Formatting

| Markdown            | Output            |
| ------------------- | ----------------- |
| `**bold**`          | **bold**          |
| `*italic*`          | *italic*          |
| `***bold italic***` | ***bold italic*** |
| `~~strikethrough~~` | ~~strikethrough~~ |
| `` `inline code` `` | `inline code`     |

Example:

```md
The **ARIMA** model consists of the parameters *p*, *d*, and *q*.
```

---

# Lists

## Unordered List

```md
- First item
- Second item
  - Nested item
  - Another nested item
```

## Ordered List

```md
1. Load the data
2. Check stationarity
3. Select model parameters
4. Fit the model
```

---

# Quotes

```md
> This is an important note.
```

Output:

> This is an important note.

---

# Code

## Inline Code

```md
The parameter `d` represents the differencing order.
```

## Code Blocks

````md
```python
from statsmodels.tsa.arima.model import ARIMA

model = ARIMA(data, order=(2,1,1))
results = model.fit()
```
````

Supported languages include:

* `python`
* `cpp`
* `c`
* `java`
* `javascript`
* `typescript`
* `bash`
* `sql`
* `json`
* `yaml`
* `r`

---

# Mathematics (LaTeX)

## Inline Equations

```md
The model is denoted as $ARIMA(p,d,q)$.
```

Example:

The model is denoted as $ARIMA(p,d,q)$.

---

## Display Equations

```md
$$
X_t =
c +
\sum_{i=1}^{p}\phi_iX_{t-i}
+
\sum_{j=1}^{q}\theta_j\varepsilon_{t-j}
+
\varepsilon_t
$$
```

---

## Common LaTeX Commands

### Subscripts

```latex
x_t
```

### Superscripts

```latex
x^{(k)}
```

### Fractions

```latex
\frac{a}{b}
```

### Summation

```latex
\sum_{i=1}^{n}
```

### Product

```latex
\prod_{i=1}^{n}
```

### Square Root

```latex
\sqrt{x}
```

### Absolute Value

```latex
|x|
```

### Greek Letters

```latex
\alpha
\beta
\gamma
\delta
\lambda
\mu
\sigma
\phi
\theta
\epsilon
```

### Logarithm

```latex
\log(x)
```

### Exponential

```latex
\exp(x)
```

### Normal Distribution

```latex
X \sim \mathcal{N}(\mu,\sigma^2)
```

---

# Tables

```md
| Parameter | Description |
|-----------|-------------|
| p | Autoregressive order |
| d | Differencing order |
| q | Moving average order |
```

---

# Links

```md
[GitHub](https://github.com)

[Statsmodels](https://www.statsmodels.org/)
```

---

# Images

```md
![ARIMA](images/arima.png)
```

Resize images using HTML:

```html
<img src="images/arima.png" width="600">
```

---

# Horizontal Rules

```md
---
```

---

# Task Lists

```md
- [x] Data cleaned
- [x] Stationarity verified
- [ ] Hyperparameters selected
- [ ] Model evaluated
```

---

# Callouts

## Note

```md
> [!NOTE]
> Additional information goes here.
```

---

## Tip

```md
> [!TIP]
> Always check stationarity before fitting an ARIMA model.
```

---

## Important

```md
> [!IMPORTANT]
> The parameter `d` specifies the number of differencing operations.
```

---

## Warning

```md
> [!WARNING]
> Non-stationary data may produce misleading results.
```

---

## Caution

```md
> [!CAUTION]
> Do not interpret coefficients without validating model assumptions.
```

---

# Collapsible Sections

```html
<details>

<summary>Mathematical Derivation</summary>

Place the complete proof or derivation here.

</details>
```

---

# HTML Support

Center text:

```html
<p align="center">

# ARIMA

</p>
```

Center images:

```html
<p align="center">
<img src="images/arima.png" width="500">
</p>
```

---

# Emojis

```md
✅ Completed

❌ Failed

⚠️ Warning

📌 Important

💡 Tip

🚀 Performance

📖 Reference
```

---

# Documentation Structure

A consistent documentation structure improves readability across projects.

```text
Model
├── Introduction
├── Motivation
├── Assumptions
├── Mathematical Background
├── Notation
├── Model Definition
├── Parameter Interpretation
├── Algorithm
├── Example
├── Advantages
├── Limitations
├── Computational Complexity
├── References
```

---

# Example Documentation Section

```md
# ARIMA

## Introduction

ARIMA is one of the most widely used statistical models for forecasting univariate time series.

## Parameters

- $p$ — autoregressive order
- $d$ — differencing order
- $q$ — moving average order

## Mathematical Model

$$
X_t =
c +
\sum_{i=1}^{p}\phi_iX_{t-i}
+
\sum_{j=1}^{q}\theta_j\varepsilon_{t-j}
+
\varepsilon_t
$$

> [!IMPORTANT]
> Ensure the time series is stationary before fitting the model.

## References

1. Box & Jenkins — *Time Series Analysis*
2. Hyndman & Athanasopoulos — *Forecasting: Principles and Practice*
```

---

# Best Practices

* Use meaningful section headings.
* Keep one topic per section.
* Prefer mathematical notation over screenshots of equations.
* Include code snippets whenever possible.
* Use tables for parameters, symbols, and notation.
* Highlight important information using GitHub callouts.
* Document assumptions before presenting equations.
* Keep terminology consistent throughout the document.
* End each document with references or further reading.
* Follow the same structure for every model to make the documentation easy to navigate.

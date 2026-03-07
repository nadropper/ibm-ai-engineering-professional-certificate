# Multiple Linear Regression

## What is Multiple Linear Regression?

In **Simple Linear Regression** (SLR), we model the relationship
between one input feature and one continuous output using a line:

```
ŷ = θ₀ + θ₁x
```

Real-world phenomena are rarely so simple. Most things we want to
predict depend on several factors at once. A house's price depends on
its size, number of bedrooms, location, and age. A patient's blood
pressure depends on weight, diet, exercise level, and genetics.

**Multiple Linear Regression** (MLR) extends SLR to any number of
input features:

```
ŷ = θ₀ + θ₁x₁ + θ₂x₂ + ··· + θₙxₙ
```

Where:
- `x₁, x₂, ..., xₙ` are the **n input features**
- `θ₀` is the **intercept** — the predicted value when all
  features equal zero
- `θ₁, θ₂, ..., θₙ` are the **coefficients**, one per feature
- `ŷ` ("y-hat") is the **predicted output**

Geometrically: SLR fits a line through 2D data. MLR with two features
fits a **plane** through 3D data. With more features it fits a
**hyperplane** — a concept we can't visualize but can compute exactly.

---

## Simple vs. Multiple Linear Regression

| Aspect           | Simple Linear Regression | Multiple Linear Regression |
|------------------|--------------------------|----------------------------|
| Input features   | 1                        | 2 or more                  |
| Model equation   | ŷ = θ₀ + θ₁x             | ŷ = θ₀ + θ₁x₁ + ··· + θₙxₙ |
| Geometry         | Line (2D)                | Plane / hyperplane         |
| # of parameters  | 2 (θ₀, θ₁)               | n + 1                      |
| Visualisation    | Easy scatter plot        | Hard/impossible above 3D   |
| Overfitting risk | Lower                    | Higher                     |
| Expressiveness   | Limited                  | Greater                    |

The core idea is identical in both cases: find the parameter values
that minimize the difference between predictions and true values. MLR
simply gives the model more information to work with.

---

## The Mathematics

### The prediction equation

For a single example with n features, the model predicts:

```
ŷ = θ₀ + θ₁x₁ + θ₂x₂ + ··· + θₙxₙ
```

### Matrix form

When training on many examples at once it is more convenient to write
this using **linear algebra**. We stack all m training examples into a
**design matrix** X, all parameters into a vector θ, and all targets
into a vector y:

```
        | 1  x₁⁽¹⁾  x₂⁽¹⁾  ···  xₙ⁽¹⁾ |       | y⁽¹⁾ |
        | 1  x₁⁽²⁾  x₂⁽²⁾  ···  xₙ⁽²⁾ |       | y⁽²⁾ |
  X  =  | ·  ·       ·            ·   |  y =  |  ·   |
        | 1  x₁⁽ᵐ⁾  x₂⁽ᵐ⁾  ···  xₙ⁽ᵐ⁾ |       | y⁽ᵐ⁾ |

  θ  =  [ θ₀  θ₁  θ₂  ···  θₙ ]ᵀ
```

The leading column of 1s absorbs the intercept term θ₀. The model for
all examples at once is then:

```
ŷ = Xθ
```

And the Mean Squared Error cost we want to minimize is:

```
MSE(θ) = (1/m) · (Xθ - y)ᵀ(Xθ - y)
```

> **Don't worry if the matrix notation looks intimidating.** It is
> just a compact way of writing many equations simultaneously. Every
> row of X is one training example, and multiplying Xθ computes the
> prediction for all examples in one shot.

---

## Estimating the Parameters

Training the model means finding the values of θ that minimize the
cost function. There are two main approaches.

### 1. Ordinary Least Squares (OLS) — the closed-form solution

OLS solves for θ analytically using the **Normal Equation**:

```
θ = (XᵀX)⁻¹ Xᵀy
```

This gives the exact optimal solution in a single step — no iteration
required.

**Pros:**
- Exact answer, no hyperparameters to tune
- No learning rate to choose, no convergence to wait for

**Cons:**
- Computing the matrix inverse scales as O(n³) in the number of
  features. It becomes very slow when n is large (e.g. thousands of
  features).
- Fails if XᵀX is not invertible, which happens when features are
  perfectly correlated (see the Multicollinearity pitfall below).

> **When to use OLS:** small-to-medium datasets with a moderate
> number of features (up to roughly a few thousand).

---

### 2. Gradient Descent — the iterative solution

Gradient Descent starts with an arbitrary θ and repeatedly moves it
in the direction that reduces the cost most:

```
θ ← θ - α · ∇MSE(θ)
```

Here α (alpha) is the **learning rate** — a small positive number
that controls how large each step is.

**Pros:**
- Scales well to very large datasets and many features
- Still works when XᵀX is not invertible
- The same algorithm used to train neural networks

**Cons:**
- Requires choosing a good learning rate (too large → diverges,
  too small → converges very slowly)
- Needs many iterations; convergence is not instant
- Sensitive to feature scale (features on larger scales dominate
  the gradient — standardize your features first)

**Variants:**

| Variant                  | Data used per step   | Behaviour              |
|--------------------------|----------------------|------------------------|
| Batch Gradient Descent   | All m examples       | Smooth but slow        |
| Stochastic GD (SGD)      | 1 random example     | Fast but noisy         |
| Mini-batch GD            | k examples (e.g. 32) | Best of both worlds    |

> **When to use Gradient Descent:** large datasets, many features,
> or when extending the same training loop to more complex models.

---

### 3. Maximum Likelihood Estimation (MLE)

If we assume the residuals (prediction errors) are normally
distributed, the MLR problem can also be derived from a probabilistic
perspective using **Maximum Likelihood Estimation**. Under this
assumption, MLE produces the same parameter estimates as OLS. MLE
becomes the more natural framing when you move into generalized
linear models (e.g. logistic regression), where the output is no
longer continuous.

---

## Interpreting the Coefficients

Each coefficient θᵢ answers the question:

> "Holding all other features constant, what is the change in ŷ
> for a one-unit increase in xᵢ?"

This **"all else equal"** interpretation is what makes MLR powerful
for causal reasoning and controlled comparisons.

**Example — a simple house price model:**

```
price = 50,000 + 200·(area_m²) + 15,000·(bedrooms)
```

- Each extra m² adds $200 to the predicted price,
  *independent of the number of bedrooms*.
- Each extra bedroom adds $15,000,
  *independent of the total area*.

**Important caveat — feature scale affects coefficient magnitude.**
A coefficient of 200 for area (measured in m²) and 200,000 for area
(measured in km²) describe the same underlying relationship. This
means you cannot directly compare coefficients across features that
are measured in different units.

**Solution:** **standardize** each feature before training (subtract
its mean, divide by its standard deviation). Standardized coefficients
are unit-free and directly comparable — a larger absolute value means
the feature has a stronger influence on the prediction.

---

## Assumptions of Multiple Linear Regression

MLR rests on a set of assumptions. Violating them doesn't always
break the model, but it can undermine both prediction accuracy and
your ability to interpret the results statistically.

### 1. Linearity
The relationship between each feature and the target must be linear
(additive and proportional). If the true relationship is curved,
the model will systematically over-predict in some regions and
under-predict in others.

**Check:** plot residuals (actual − predicted) against each feature.
Patterns in residuals signal non-linearity.

### 2. Independence of observations
Each row in your dataset should be independent of every other row.
Time-series data (where today's value depends on yesterday's) and
clustered data (students within schools) often violate this.

### 3. Homoscedasticity
The variance of the residuals should be roughly constant across all
predicted values. If errors grow as predictions grow (a "fan" shape
in the residual plot), confidence intervals and p-values will be
unreliable.

### 4. Normality of residuals
The prediction errors should be approximately normally distributed.
This matters primarily for statistical tests on the coefficients
(t-tests, confidence intervals). It is less critical if your only
goal is predictive accuracy.

### 5. No perfect multicollinearity
No feature should be an exact linear combination of other features
(see Pitfalls below). Near-perfect collinearity, while not a
technical violation, is still a serious practical problem.

> **Practical priority:** Assumptions 1 and 5 have the largest
> effect on prediction quality. Assumptions 2, 3, and 4 matter most
> when you want to interpret p-values and confidence intervals.

---

## Pitfalls of Multiple Linear Regression

### Pitfall 1: Multicollinearity

**What it is:** two or more input features are strongly correlated
with each other.

**Example:** including both "total floor area" and "living room area"
in a house price model. These features share almost the same
information.

**Why it is a problem:**
- The model cannot reliably separate each feature's contribution.
  Small data changes cause large swings in the estimated coefficients.
- OLS becomes numerically unstable — XᵀX approaches singularity.
- Coefficients are difficult or impossible to interpret meaningfully.

**How to detect it:** compute the **Variance Inflation Factor (VIF)**
for each feature. A VIF above 10 is a common warning threshold.

**How to fix it:**
- Remove one of the correlated features.
- Combine correlated features (e.g. use their average or a PCA
  component).
- Use **Ridge Regression** (L2 regularization), which is designed to
  handle correlated features gracefully.

---

### Pitfall 2: Overfitting

**What it is:** the model learns the training data too well —
including its noise — and fails to generalize to new data.

**Why it happens in MLR:** each feature you add gives the model more
degrees of freedom. With enough features relative to the number of
training examples, the model can memorize the training set rather than
learning the underlying pattern.

**Signs:**
- Training error is low, but test error is substantially higher.
- Adding more training data steadily improves test performance.

**How to fix it:**
- Use fewer features (feature selection).
- Collect more training data.
- Apply **regularization**: Ridge regression penalizes large
  coefficients (shrinks them toward zero); Lasso regression can
  shrink some coefficients all the way to zero, effectively selecting
  features automatically.

---

### Pitfall 3: Underfitting

The opposite problem — the model is too simple to capture the true
pattern in the data.

**Signs:** both training error and test error are high.

**How to fix it:**
- Add more relevant features.
- Introduce **interaction terms** (e.g. x₁ · x₂) or **polynomial
  features** (e.g. x₁²) if the true relationship is non-linear.
- Switch to a more expressive model class.

---

### Pitfall 4: Extrapolation

Linear regression extends the best-fit hyperplane infinitely. When
you provide feature values far outside the training data's range, the
model still produces a number — but there is no reason to trust it.

**Example:** a model trained on 1–8 liter engines predicts CO2 for a
20 liter engine. The linear trend may not hold outside the training
range.

**Rule of thumb:** never trust predictions outside the range of values
the model was trained on without additional validation.

---

### Pitfall 5: Irrelevant features

Including features with no real relationship to the target adds noise,
can degrade performance, makes the model slower to train, and makes
it harder to interpret.

**How to avoid it:**
- Start with domain knowledge: does this feature make physical or
  logical sense as a predictor?
- Use feature importance scores from regularization: Lasso regression
  shrinks irrelevant features' coefficients to exactly zero.

---

### Pitfall 6: Ignoring feature scaling

Features on very different scales (e.g. income in tens of thousands
vs. age in years vs. number of rooms) do not affect OLS's final
predictions, but they do affect:

- **Gradient Descent convergence** — large-scale features dominate
  the gradient, causing slow or oscillating convergence.
- **Coefficient interpretability** — coefficients are not comparable
  across features measured in different units.

**Fix:** standardize (zero mean, unit variance) or min-max normalize
your features before training.

---

## Common Uses of Multiple Linear Regression

MLR is one of the most widely applied statistical models across
virtually every quantitative field.

### Real Estate
Predicting property prices from area, location, number of rooms, age
of the building, proximity to transit, and school quality.

### Economics and Finance
- Estimating GDP from investment, consumption, and government
  spending (macroeconomic models).
- Predicting stock or asset returns from market factors — the
  foundation of factor models such as the Fama-French three-factor
  model.
- Credit scoring: estimating default probability from income, debt,
  payment history, and other financial variables.

### Healthcare and Medicine
- Modeling a patient's risk score from age, BMI, blood pressure,
  cholesterol, and lifestyle factors.
- Estimating a drug's effect on an outcome while **controlling for**
  age, weight, and comorbidities. This "controlling for" is one of
  MLR's most important practical uses.

### Engineering
- Predicting vehicle fuel consumption from speed, load, road
  gradient, and wind resistance.
- Estimating a component's remaining useful life from temperature,
  vibration, and usage hours.

### Marketing and Attribution
- Attributing sales lift to spending across multiple channels (TV,
  digital, radio, out-of-home).
- Estimating price elasticity while accounting for promotions,
  seasonality, and competitor pricing.

### Environmental Science
- Modeling CO2 concentration or air quality from temperature,
  humidity, wind speed, and industrial output.
- Predicting crop yield from rainfall, soil composition, and
  temperature across growing seasons.

---

## Summary

| Topic                  | Key point                                           |
|------------------------|-----------------------------------------------------|
| Core idea              | Extend SLR to n features; still fits a hyperplane   |
| Model equation         | ŷ = θ₀ + θ₁x₁ + ··· + θₙxₙ                          |
| Parameter estimation   | OLS (exact, fast for small n) or Gradient Descent   |
| Coefficient meaning    | Change in ŷ per 1-unit increase in xᵢ, all else =   |
| Key assumptions        | Linearity, independence, homoscedasticity,          |
|                        | normality of residuals, no multicollinearity        |
| Main pitfalls          | Multicollinearity, overfitting, irrelevant features |
| Remedy for overfitting | Regularisation (Ridge / Lasso), feature selection   |
| Common uses            | Pricing, risk, attribution, forecasting, science    |

Multiple linear regression is a foundational model. Understanding it
deeply — its assumptions, its failure modes, and when to trust its
output — builds the intuition you need before moving on to more
complex models like regularized regression, decision trees, or neural
networks.

# 📚 Mathematical Modeling of Biological Systems - Complete Study Guide

> **Comprehensive notes for MSc Bioinformatics | Exam-Ready Edition**  
> *Updated with detailed examples, visualizations, and structured content*

---

## 📑 Table of Contents

1. [Introduction to Mathematical Modeling](#1-introduction-to-mathematical-modeling)
2. [Types of Mathematical Models](#2-types-of-mathematical-models)
3. [Levels of Biological Modeling](#3-levels-of-biological-modeling)
4. [The Modeling Process](#4-the-modeling-process)
5. [Growth Models](#5-growth-models)
6. [Enzyme Kinetics & Substrate Constraints](#6-enzyme-kinetics--substrate-constraints)
7. [Population Interaction Models](#7-population-interaction-models)
8. [Oscillations & Biological Rhythms](#8-oscillations--biological-rhythms)
9. [Mathematical Techniques & Methods](#9-mathematical-techniques--methods)
10. [Practical Applications](#10-practical-applications)
11. [Advanced Topics](#11-advanced-topics)
12. [Quick Reference & Formulas](#12-quick-reference--formulas)

---

# 1️⃣ Introduction to Mathematical Modeling

## 🎯 What is Mathematical Modeling?

**Mathematical modeling** is the art and science of translating biological phenomena into mathematical language to understand, predict, and optimize biological systems.

### Key Characteristics

| Characteristic | Description | Example |
|---------------|-------------|---------|
| **Quantitative** | Uses numbers and equations | Population size = 1000 organisms |
| **Predictive** | Forecasts future states | Bacteria will double in 20 min |
| **Simplified** | Captures essential features | Ignores minor variations |
| **Testable** | Can be validated with data | Compare model vs experiments |
| **Iterative** | Refined based on feedback | Update parameters after testing |

### 🎯 Purpose of Mathematical Models

graph TD
A[Mathematical Model] --> B[🔍 Understand Mechanisms]
A --> C[📊 Make Predictions]
A --> D[🧪 Test Hypotheses]
A --> E[⚙️ Optimize Processes]
A --> F[💡 Discover Patterns]

text
B --> G[Gene regulation networks]
C --> H[Population forecasts]
D --> I[Drug efficacy trials]
E --> J[Fermentation yield]
F --> K[Periodic oscillations]
text

### 🧬 Why Biology Needs Mathematical Models

| Challenge | Why Model? | Benefit |
|-----------|------------|---------|
| **Complexity** | Too many interacting components | Simplify to essentials |
| **Hidden Variables** | Can't measure everything | Infer from observables |
| **Experimentation Limits** | Expensive/unethical experiments | Simulate in silico |
| **Timescales** | Too slow or too fast | Compress/expand time |
| **Integration** | Multiple organizational levels | Connect scales |

---

# 2️⃣ Types of Mathematical Models

## 📊 Classification by Approach

### 🎲 Deterministic vs Stochastic Models

graph LR
A[Mathematical Models] --> B[Deterministic]
A --> C[Stochastic]

text
B --> D[Same input = Same output]
B --> E[No randomness]
B --> F[Predictable]

C --> G[Same input = Different outputs]
C --> H[Includes randomness]
C --> I[Probabilistic]

style B fill:#90EE90
style C fill:#FFB6C1
text

#### Deterministic Models ✅

**Characteristics:**
- Same initial conditions → Same outcome
- No random variation
- Uses fixed parameters
- Reproducible results

**Mathematical Form:**
$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)$$

**Examples:**
- 🧫 Bacterial growth in controlled conditions
- 🧬 Enzyme kinetics
- ❤️ Blood circulation models
- 🌱 Plant growth under constant environment

**When to Use:**
- ✅ Large populations (law of large numbers)
- ✅ Consistent environmental conditions
- ✅ Predictable behavior needed
- ✅ System behaves regularly

#### Stochastic Models 🎲

**Characteristics:**
- Random variations included
- Probability distributions
- Multiple possible outcomes
- Accounts for noise

**Mathematical Form:**
$$N(t+\Delta t) = N(t) + \text{Poisson}(\lambda \Delta t) - \text{Poisson}(\mu \Delta t)$$

**Examples:**
- 🧬 Genetic drift in small populations
- 🦠 Viral mutations
- 🧪 Molecular collisions
- 🎯 Gene expression noise

**When to Use:**
- ✅ Small populations (stochastic effects matter)
- ✅ Inherent randomness (quantum, molecular)
- ✅ Individual variation important
- ✅ Uncertainty quantification needed

---

### ⏰ Discrete vs Continuous Models

graph TD
A[Time Representation] --> B[Discrete Time]
A --> C[Continuous Time]

text
B --> D[t = 0, 1, 2, 3, ...]
B --> E[Difference Equations]
B --> F[Example: Annual census]

C --> G[t = any real number]
C --> H[Differential Equations]
C --> I[Example: Growth rate]

style B fill:#87CEEB
style C fill:#FFA07A
text

#### Discrete Models 🔢

**Definition:** Time progresses in distinct steps (jumps)

**Mathematical Form:**
$$N_{t+1} = N_t + rN_t\left(1 - \frac{N_t}{K}\right)$$

**Notation:**
- $N_t$ = Population at time step $t$
- $N_{t+1}$ = Population at next time step
- Difference equation (not differential)

**Examples:**
- 📅 Yearly population surveys
- 🦋 Insect generations (discrete life cycles)
- 🌾 Seasonal plant growth
- 📊 Monthly disease counts

**Advantages:**
- ✅ Matches data collection (surveys)
- ✅ Easier to understand (counting)
- ✅ Natural for organisms with discrete generations
- ✅ Simple computational implementation

#### Continuous Models 📈

**Definition:** Time flows smoothly without jumps

**Mathematical Form:**
$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)$$

**Notation:**
- $\frac{dN}{dt}$ = Instantaneous rate of change
- Derivative with respect to time
- Differential equation

**Examples:**
- 🧫 Bacterial growth (continuous reproduction)
- 💓 Heart rate dynamics
- 🧬 Enzyme reactions
- 🌡️ Body temperature regulation

**Advantages:**
- ✅ Realistic for overlapping generations
- ✅ Mathematical analysis tools available
- ✅ Smooth predictions
- ✅ Captures instantaneous changes

---

### 🔧 Representation-Based Classification

#### 1️⃣ Verbal Models 💬

**Description:** Qualitative explanations in words

**Example:**  
> "Predators increase when prey are abundant. When predators become too numerous, prey decline. With fewer prey, predators starve and their numbers drop. This allows prey to recover, restarting the cycle."

**Advantages:**
- ✅ Easy to understand
- ✅ No math needed
- ✅ Good for communication

**Disadvantages:**
- ❌ Not quantitative
- ❌ No precise predictions
- ❌ Ambiguous

#### 2️⃣ Diagrammatic Models 📊

**Description:** Visual representations with flowcharts and diagrams

**Example: Predator-Prey System**

graph LR
A[🐰 Prey Population] -->|Eaten by| B[🦊 Predators]
B -->|Increases with| A
A -->|Birth Rate| A
B -->|Death Rate| C[💀 Predator Death]
A -->|High Prey| D[More Food for Predators]
D --> B
B -->|High Predators| E[More Predation]
E --> F[Prey Decline]
F --> G[Predator Starvation]
G --> A

text
style A fill:#90EE90
style B fill:#FFB6C1
text

**Advantages:**
- ✅ Clear system overview
- ✅ Shows relationships
- ✅ Intuitive

**Disadvantages:**
- ❌ Limited for precise predictions
- ❌ Qualitative only
- ❌ Complex systems become messy

#### 3️⃣ Mathematical Models 🧮

**Description:** Equations and formulas

**Example:**
$$\frac{dx}{dt} = \alpha x - \beta xy \quad \text{(Prey)}$$
$$\frac{dy}{dt} = \delta xy - \gamma y \quad \text{(Predators)}$$

**Advantages:**
- ✅ Precise and quantitative
- ✅ Predictive power
- ✅ Can be simulated

**Disadvantages:**
- ❌ Requires math expertise
- ❌ May oversimplify
- ❌ Assumptions needed

---

## 📊 Comparison Table: Model Types

| Feature | Deterministic | Stochastic | Discrete | Continuous |
|---------|---------------|------------|----------|------------|
| **Time** | Any | Any | Steps (0,1,2,...) | Smooth flow |
| **Randomness** | ❌ No | ✅ Yes | Can be either | Can be either |
| **Output** | Single trajectory | Distribution | Sequence of values | Smooth curve |
| **Equation Type** | Fixed equations | Probability equations | Difference equations | Differential equations |
| **Example** | Logistic growth | Genetic drift | Yearly census | Bacterial growth |
| **Complexity** | ⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ |
| **Best For** | Large systems | Small systems | Discrete events | Continuous processes |

---

# 3️⃣ Levels of Biological Modeling

Biological systems are hierarchically organized from molecules to ecosystems. Mathematical models can target any organizational level.

graph TD
A[🧬 Molecular Level] --> B[🔬 Cellular Level]
B --> C[🧫 Tissue/Organ Level]
C --> D[🧍 Organism Level]
D --> E[👥 Population Level]
E --> F[🌍 Ecosystem Level]

text
A1[DNA, RNA, Proteins] -.-> A
B1[Cell metabolism, Division] -.-> B
C1[Organ function, Tissues] -.-> C
D1[Growth, Behavior] -.-> D
E1[Population dynamics] -.-> E
F1[Food webs, Energy flow] -.-> F

style A fill:#E6E6FA
style B fill:#FFE4E1
style C fill:#F0E68C
style D fill:#98FB98
style E fill:#87CEEB
style F fill:#DDA0DD
text

## 🔬 Level 1: Molecular Level

**Scale:** Nanometers (10⁻⁹ m) to micrometers (10⁻⁶ m)  
**Timescale:** Milliseconds to minutes

### Components
- 🧬 DNA, RNA molecules
- 🧪 Proteins and enzymes
- ⚡ Chemical reactions
- 🔗 Molecular interactions

### Example Models
- **Enzyme kinetics:** Michaelis-Menten equation
- **Gene expression:** Transcription and translation rates
- **Protein folding:** Energy landscapes
- **Molecular binding:** Ligand-receptor interactions

### Example: Enzyme-Substrate Binding
$$E + S \xrightarrow{k_1} ES \xrightarrow{k_2} E + P$$

Where:
- $E$ = Enzyme
- $S$ = Substrate
- $ES$ = Enzyme-substrate complex
- $P$ = Product
- $k_1, k_2$ = Rate constants

**Model Equation:**
$$v = \frac{V_{max}[S]}{K_m + [S]}$$

---

## 🔬 Level 2: Cellular Level

**Scale:** Micrometers (10⁻⁶ m)  
**Timescale:** Seconds to hours

### Components
- 🧫 Single cells
- ⚙️ Cellular metabolism
- 🔄 Cell cycle and division
- 📡 Signal transduction pathways

### Example Models
- **Cell growth:** Logistic growth within cells
- **Cell cycle:** Cyclin-CDK oscillations
- **Signal transduction:** MAPK cascade
- **Calcium dynamics:** Oscillatory calcium signaling

### Example: Cell Division Model
$$\frac{dN}{dt} = \mu N$$

Where:
- $N$ = Cell number
- $\mu$ = Specific growth rate (divisions/time)

**With Death:**
$$\frac{dN}{dt} = (\mu - d)N = rN$$

Where $r = \mu - d$ (net growth rate)

---

## 🧫 Level 3: Tissue/Organ Level

**Scale:** Millimeters to centimeters  
**Timescale:** Minutes to days

### Components
- 🫀 Organs (heart, liver, brain)
- 🧠 Tissue organization
- ⚡ Electrical conduction (neurons)
- 🌊 Diffusion and transport

### Example Models
- **Heart dynamics:** Cardiac electrical conduction
- **Neural networks:** Action potential propagation
- **Tumor growth:** Avascular and vascular phases
- **Oxygen diffusion:** Fick's law in tissues

### Example: Oxygen Diffusion in Tissue
$$\frac{\partial C}{\partial t} = D \nabla^2 C - R$$

Where:
- $C$ = Oxygen concentration
- $D$ = Diffusion coefficient
- $R$ = Consumption rate
- $\nabla^2$ = Laplacian (spatial derivative)

---

## 🧍 Level 4: Organism Level

**Scale:** Centimeters to meters  
**Timescale:** Hours to years

### Components
- 🌱 Individual organisms
- 📈 Growth and development
- 🧬 Physiology and metabolism
- 🛡️ Immune response

### Example Models
- **Individual growth:** Von Bertalanffy growth model
- **Metabolism:** Energy balance equations
- **Disease progression:** Infection dynamics within host
- **Aging:** Gompertz mortality model

### Example: Von Bertalanffy Growth
$$\frac{dL}{dt} = k(L_\infty - L)$$

**Solution:**
$$L(t) = L_\infty\left(1 - e^{-kt}\right)$$

Where:
- $L(t)$ = Length at time $t$
- $L_\infty$ = Asymptotic maximum length
- $k$ = Growth rate coefficient

**Graph:**
graph LR
A[Birth] -->|Fast Growth| B[Juvenile]
B -->|Slowing Growth| C[Adult]
C -->|Asymptotic| D[Maximum Size L∞]

text
style A fill:#FFE4E1
style B fill:#98FB98
style C fill:#87CEEB
style D fill:#DDA0DD
text

---

## 👥 Level 5: Population Level

**Scale:** Meters to kilometers  
**Timescale:** Years to generations

### Components
- 👥 Groups of same species
- 📊 Population dynamics
- 🦠 Disease spread (epidemiology)
- 🧬 Evolution and adaptation

### Example Models
- **Population growth:** Logistic growth model
- **Predator-prey:** Lotka-Volterra equations
- **Epidemics:** SIR model
- **Genetic drift:** Wright-Fisher model

### Example: Logistic Population Growth
$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)$$

**Phases:**
1. **Lag:** Slow initial growth
2. **Exponential:** Rapid growth phase
3. **Stationary:** Plateau at carrying capacity $K$

---

## 🌍 Level 6: Ecosystem Level

**Scale:** Kilometers and beyond  
**Timescale:** Years to centuries

### Components
- 🌳 Multiple species interactions
- 🍃 Food webs and nutrient cycles
- ⚡ Energy flow
- 🌐 Community dynamics

### Example Models
- **Food webs:** Multi-species interaction networks
- **Nutrient cycling:** Carbon, nitrogen cycles
- **Energy flow:** Trophic level models
- **Biodiversity:** Species-area relationships

### Example: Simple Food Chain
$$\frac{dP}{dt} = rP - aPC \quad \text{(Plant)}$$
$$\frac{dH}{dt} = bPC - cHC - dH \quad \text{(Herbivore)}$$
$$\frac{dC}{dt} = eHC - fC \quad \text{(Carnivore)}$$

---

## 🔍 Cross-Level Modeling Challenges

| Challenge | Description | Solution Approach |
|-----------|-------------|-------------------|
| **Scale Separation** | Processes at different levels | Multi-scale modeling |
| **Emergent Properties** | System behavior > sum of parts | Agent-based models |
| **Data Integration** | Combine molecular + population data | Hierarchical models |
| **Computational Cost** | Simulating all levels expensive | Coarse-graining |
| **Parameter Variability** | Parameters differ across scales | Scale-dependent parameters |

---

# 4️⃣ The Modeling Process

Mathematical modeling is an iterative cycle involving multiple stages from problem definition to application.

graph TD
A[🎯 Stage 1: Problem Definition] --> B[📐 Stage 2: Model Formulation]
B --> C[💻 Stage 3: Implementation]
C --> D[✅ Stage 4: Testing & Validation]
D --> E[🚀 Stage 5: Application & Analysis]
E --> F{Model Valid?}
F -->|No| B
F -->|Yes| G[📊 Use Model]
G --> H[🔄 Refine as Needed]
H --> B

text
style A fill:#FFE4E1
style B fill:#E6E6FA
style C fill:#98FB98
style D fill:#FFB6C1
style E fill:#87CEEB
text

---

## 🎯 Stage 1: Problem Definition

### Objective
Define the biological question clearly and establish goals for the model.

### Activities Checklist
- ✅ **Identify system of interest** (e.g., bacterial population, enzyme reaction)
- ✅ **Specify goals:** Predict? Understand mechanism? Optimize?
- ✅ **Gather available data** (experimental measurements)
- ✅ **Review literature** (existing models, known mechanisms)
- ✅ **Define boundaries** (what's included/excluded?)
- ✅ **List key variables** (population size, concentrations, time)

### Example: Bacterial Growth Study

**Question:** How does a bacterial population grow in a nutrient-limited environment?

**Goals:**
- 🎯 Predict population size over time
- 🔍 Understand effect of nutrient limitation
- ⚙️ Optimize fermentation conditions

**Available Data:**
- Initial population: $N_0 = 10^6$ cells
- Nutrient concentration: $[S] = 5$ g/L
- Growth rate measurements

**Boundaries:**
- Include: Growth, nutrient consumption
- Exclude: Genetic mutations, pH effects

---

## 📐 Stage 2: Model Formulation

### Objective
Translate biological system into mathematical equations.

### Activities
1. **Identify variables**
   - State variables (change over time): $N(t)$, $S(t)$
   - Independent variable (time): $t$
   
2. **Choose model type**
   - Deterministic or stochastic?
   - Discrete or continuous?
   - ODE, PDE, or difference equations?

3. **List assumptions**
   - Homogeneous population (no subgroups)
   - Well-mixed (no spatial variation)
   - Constant temperature
   - No cell death

4. **Write equations based on mechanisms**
   - Growth depends on nutrients: $\mu = \mu_{max} \frac{S}{K_s + S}$
   - Nutrient consumption proportional to growth

5. **Define parameters**
   - $\mu_{max}$ = Maximum specific growth rate
   - $K_s$ = Half-saturation constant
   - $Y$ = Yield coefficient

6. **Specify initial conditions**
   - $N(0) = N_0$
   - $S(0) = S_0$

### Example Model

**Bacterial growth with nutrient limitation:**

$$\frac{dN}{dt} = \mu_{max} \frac{S}{K_s + S} \cdot N$$

$$\frac{dS}{dt} = -\frac{1}{Y} \mu_{max} \frac{S}{K_s + S} \cdot N$$

Where:
- $N$ = Bacterial population (cells/mL)
- $S$ = Substrate (nutrient) concentration (g/L)
- $\mu_{max}$ = Max specific growth rate (1/hr)
- $K_s$ = Half-saturation constant (g/L)
- $Y$ = Yield coefficient (cells/g)

---

## 💻 Stage 3: Model Implementation

### Objective
Convert mathematical equations into working simulation code.

### Activities
1. **Choose platform**
   - Python (NumPy, SciPy) 🐍
   - MATLAB/Octave
   - R (deSolve package)
   - Julia

2. **Implement numerical solver**
   - Euler method (simple, less accurate)
   - Runge-Kutta 4 (RK4) - standard choice
   - Built-in solvers (odeint, solve_ivp)

3. **Write code**
import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

def model(y, t, mu_max, Ks, Y):
N, S = y
dNdt = mu_max * S / (Ks + S) * N
dSdt = -1/Y * mu_max * S / (Ks + S) * N
return [dNdt, dSdt]

Parameters
mu_max = 0.5 # 1/hr
Ks = 0.1 # g/L
Y = 1e8 # cells/g

Initial conditions
N0 = 1e6 # cells/mL
S0 = 5.0 # g/L
y0 = [N0, S0]

Time span
t = np.linspace(0, 20, 200) # 0 to 20 hours

Solve
solution = odeint(model, y0, t, args=(mu_max, Ks, Y))
N = solution[:, 0]
S = solution[:, 1]

Plot
plt.figure(figsize=(12, 5))
plt.subplot(1, 2, 1)
plt.plot(t, N, 'b-', linewidth=2)
plt.xlabel('Time (hours)')
plt.ylabel('Cell Count (cells/mL)')
plt.title('Bacterial Growth')
plt.grid(True)

plt.subplot(1, 2, 2)
plt.plot(t, S, 'r-', linewidth=2)
plt.xlabel('Time (hours)')
plt.ylabel('Substrate (g/L)')
plt.title('Nutrient Depletion')
plt.grid(True)
plt.tight_layout()
plt.show()

text

4. **Debug and test**
- Check for syntax errors
- Verify units match
- Test with simple cases (analytical solutions)

5. **Create visualizations**
- Time series plots
- Phase plane diagrams
- Parameter sensitivity plots

---

## ✅ Stage 4: Testing & Validation

### Objective
Evaluate model performance against experimental data.

### Key Activities

#### 1. Qualitative Validation ✅
- Does model behavior make biological sense?
- Are trends correct (increase/decrease)?
- Does model capture known phenomena?

#### 2. Quantitative Validation 📊
- Compare model predictions with data
- Calculate error metrics

**Common Metrics:**

| Metric | Formula | Interpretation |
|--------|---------|----------------|
| **SSE** (Sum of Squared Errors) | $\sum_{i=1}^{n}(y_i - \hat{y}_i)^2$ | Lower is better |
| **RMSE** (Root Mean Square Error) | $\sqrt{\frac{1}{n}\sum_{i=1}^{n}(y_i - \hat{y}_i)^2}$ | Same units as data |
| **R²** (Coefficient of Determination) | $1 - \frac{SS_{res}}{SS_{tot}}$ | 0 to 1 (1 = perfect) |
| **MAPE** (Mean Absolute % Error) | $\frac{100}{n}\sum_{i=1}^{n}\left|\frac{y_i - \hat{y}_i}{y_i}\right|$ | Percentage error |

#### 3. Sensitivity Analysis 🔍
Test how changes in parameters affect output.

**Method:**
1. Vary each parameter ±10%, ±20%, ±50%
2. Observe effect on predictions
3. Identify most influential parameters
4. Focus experimental effort on measuring these accurately

**Example:**
Sensitivity analysis for mu_max
mu_values = [0.4, 0.45, 0.5, 0.55, 0.6] # ±20%

for mu in mu_values:
solution = odeint(model, y0, t, args=(mu, Ks, Y))
plt.plot(t, solution[:, 0], label=f'μ_max = {mu}')

plt.legend()
plt.xlabel('Time (hours)')
plt.ylabel('Cell Count')
plt.title('Sensitivity to Growth Rate')
plt.show()

text

#### 4. Model Refinement 🔄
- If validation fails → revise assumptions
- Add missing components
- Adjust parameter values
- Simplify if overfitted

---

## 🚀 Stage 5: Application & Analysis

### Objective
Use validated model to gain biological insights and make predictions.

### Activities

#### 1. Scenario Analysis 🧪
Test "what-if" questions:
- What if nutrient concentration doubled?
- What if temperature increased by 5°C?
- What if we add an inhibitor?

#### 2. Parameter Optimization ⚙️
Find optimal conditions:
- Maximize cell yield
- Minimize time to target population
- Optimize cost-effectiveness

#### 3. Prediction 🔮
Forecast future states:
- Population size at 48 hours
- Time to reach stationary phase
- Final substrate concentration

#### 4. Hypothesis Testing 🧬
Evaluate competing hypotheses:
- Does nutrient limitation explain plateau?
- Is death rate negligible?
- Do cells adapt growth rate?

#### 5. Communication 📢
- Document assumptions and limitations
- Create clear visualizations
- Write reports for stakeholders
- Publish findings

---

## 🔄 Iterative Nature of Modeling

graph LR
A[Problem] --> B[Model v1]
B --> C[Test]
C --> D{Valid?}
D -->|No| E[Refine Assumptions]
E --> F[Model v2]
F --> C
D -->|Yes| G[Apply Model]
G --> H[New Questions]
H --> A

text
style D fill:#FFB6C1
style G fill:#90EE90
text

**Key Insight:** Modeling is NOT linear—expect multiple iterations!

---

## 🎯 Sources of Model Error

Understanding where models can go wrong helps improve them.

### ❌ Type 1: Neglected Effects

**Definition:** Relevant biological factors excluded from model

**Examples:**
- Ignoring temperature effects on growth
- Not including predators in population model
- Excluding genetic mutations
- Forgetting spatial heterogeneity

**Impact:** Model systematically biased

**Solution:** 
- Review biological literature
- Consult domain experts
- Test model against diverse conditions
- Add missing terms if error large

---

### ❌ Type 2: Unmodeled Influences

**Definition:** External factors affecting system not included

**Examples:**
- Natural disasters (wildfires, floods)
- Human interventions (harvesting, drugs)
- Climate change
- Policy changes

**Impact:** Unexpected deviations from predictions

**Solution:**
- Acknowledge limitations
- Include stochastic terms for uncertainty
- Build scenario-based models
- Update model when conditions change

---

### ❌ Type 3: Parameter Uncertainty

**Definition:** Parameter values not precisely known

**Examples:**
- Growth rate varies between experiments
- Carrying capacity depends on environment
- Reaction rates temperature-dependent

**Impact:** Prediction uncertainty

**Solution:**
- Measure parameters carefully
- Use parameter ranges (confidence intervals)
- Sensitivity analysis
- Bayesian parameter estimation

---

### ❌ Type 4: Structural Error

**Definition:** Wrong functional form chosen

**Examples:**
- Using exponential growth when logistic appropriate
- Linear relationship when nonlinear
- Discrete model when continuous better

**Impact:** Poor fit even with optimal parameters

**Solution:**
- Test multiple model structures
- Compare using AIC, BIC criteria
- Validate functional forms with data
- Consider mechanistic basis

---

## 📊 Model Selection Criteria

| Criterion | Formula | Interpretation | Use Case |
|-----------|---------|----------------|----------|
| **AIC** | $-2\ln(L) + 2k$ | Lower is better | Balance fit vs complexity |
| **BIC** | $-2\ln(L) + k\ln(n)$ | Lower is better | Penalizes complexity more |
| **Adjusted R²** | $1 - \frac{(1-R^2)(n-1)}{n-k-1}$ | Higher is better | Accounts for # parameters |

Where:
- $L$ = Likelihood
- $k$ = Number of parameters
- $n$ = Number of data points

---

# 5️⃣ Growth Models

Growth models describe how populations or individuals change in size over time. They are fundamental to biology, ecology, and medicine.

graph TD
A[Growth Models] --> B[📈 Unlimited Growth]
A --> C[📊 Limited Growth]

text
B --> D[Exponential/Malthusian]

C --> E[Logistic]
C --> F[Von Bertalanffy]
C --> G[Gompertz]

style B fill:#FFB6C1
style C fill:#90EE90
text

---

## 📈 Unlimited Growth (Exponential Model)

### 🧬 Malthusian Growth Model

**Concept:** Population grows without restrictions—ideal conditions with unlimited resources.

### Assumptions ✅
- ✅ Unlimited resources (food, space, oxygen)
- ✅ No predators or competitors
- ✅ No diseases
- ✅ Constant birth and death rates
- ✅ Homogeneous population (no age structure)
- ✅ Continuous reproduction

### Mathematical Formulation

**Differential Equation:**
$$\frac{dN}{dt} = rN$$

**Parameters:**
- $N(t)$ = Population size at time $t$
- $t$ = Time
- $r$ = Intrinsic growth rate = (birth rate - death rate)
- $\frac{dN}{dt}$ = Rate of population change

**Analytical Solution:**
$$N(t) = N_0 e^{rt}$$

Where:
- $N_0$ = Initial population at $t = 0$
- $e$ ≈ 2.71828 (Euler's number)

### 📊 Exponential Growth Characteristics

**Graph Shape:** J-curve (exponential)

graph LR
A[Time 0: N₀] --> B[Time 1: N₀eʳ]
B --> C[Time 2: N₀e²ʳ]
C --> D[Time 3: N₀e³ʳ]
D --> E[...]
E --> F[∞: Unbounded]

text
style A fill:#FFE4E1
style F fill:#FF6B6B
text

**Key Features:**
- ⏳ **Slow start** when population small
- 🚀 **Accelerating growth** (population increases faster over time)
- ♾️ **Unbounded** (theoretically infinite)
- 📏 **Constant doubling time**

### Doubling Time ⏰

**Formula:**
$$t_{double} = \frac{\ln(2)}{r} = \frac{0.693}{r}$$

**Example:**
If $r = 0.1$ per hour:
$$t_{double} = \frac{0.693}{0.1} = 6.93 \text{ hours}$$

Population doubles every ~7 hours!

### Growth Rate Interpretations 📊

| Growth Rate ($r$) | Meaning | Example |
|-------------------|---------|---------|
| $r > 0$ | Population increasing | Bacteria in fresh broth |
| $r = 0$ | Population constant | Stable environment |
| $r < 0$ | Population decreasing | Overharvested fish |
| $r >> 1$ | Very rapid growth | Viral replication |

### 🧪 Real-World Examples

**Where Exponential Growth Occurs:**
1. 🦠 **Bacteria** in fresh nutrient broth (initial phase)
2. 🍞 **Yeast** in fermentation tanks (early stage)
3. 🎗️ **Cancer cells** in early tumor formation
4. 🐀 **Invasive species** in new environments (no predators)
5. 🦠 **Viral replication** without immune response
6. 💸 **Compound interest** in finance

### ⚠️ Why Exponential Growth Fails Long-Term

| Limitation | Reality Check |
|------------|---------------|
| **Resources finite** | Food, space, nutrients run out |
| **Waste accumulates** | Toxic byproducts build up |
| **Competition increases** | Crowding effects emerge |
| **Predators appear** | Natural enemies invade |
| **Disease spreads** | High density → epidemics |

### 📝 Example Problem

**Question:** A bacterial culture starts with 1000 cells and grows at $r = 0.3$ per hour. How many cells after 5 hours?

**Solution:**
$$N(5) = 1000 \times e^{0.3 \times 5} = 1000 \times e^{1.5}$$
$$N(5) = 1000 \times 4.48 = 4,482 \text{ cells}$$

**Doubling time:**
$$t_{double} = \frac{0.693}{0.3} = 2.31 \text{ hours}$$

---

## 📊 Limited Growth Models

### 🔄 Logistic Growth Model

**Concept:** Population growth slows as it approaches environmental carrying capacity. Most realistic model for confined populations.

### Assumptions ✅
- ✅ Limited resources (carrying capacity $K$)
- ✅ Competition increases with population density
- ✅ Growth rate decreases as $N$ approaches $K$
- ✅ No time lags in response
- ✅ Homogeneous environment

### Mathematical Formulation

**Differential Equation:**
$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)$$

**Parameters:**
- $N(t)$ = Population at time $t$
- $r$ = Intrinsic growth rate
- $K$ = Carrying capacity (maximum sustainable population)
- $\left(1 - \frac{N}{K}\right)$ = Environmental resistance factor

### 🧮 Understanding the Logistic Equation

**Breaking it down:**

$$\underbrace{\frac{dN}{dt}}_{\text{Growth rate}} = \underbrace{rN}_{\text{Exponential term}} \times \underbrace{\left(1 - \frac{N}{K}\right)}_{\text{Limiting factor}}$$

**Behavior at Different Population Sizes:**

| Condition | $\frac{N}{K}$ | Limiting Factor | Growth Rate | Interpretation |
|-----------|---------------|-----------------|-------------|----------------|
| $N \ll K$ | ≈ 0 | ≈ 1 | $\approx rN$ | Nearly exponential |
| $N = \frac{K}{2}$ | 0.5 | 0.5 | $\frac{rK}{4}$ | Maximum growth rate |
| $N = K$ | 1 | 0 | 0 | Zero growth (equilibrium) |
| $N > K$ | > 1 | < 0 | Negative | Population decreases |

### Analytical Solution 📐

$$N(t) = \frac{K}{1 + \left(\frac{K-N_0}{N_0}\right)e^{-rt}}$$

Or equivalently:
$$N(t) = \frac{K}{1 + Ae^{-rt}}$$

Where $A = \frac{K - N_0}{N_0}$

### 📊 Logistic Growth Phases

graph LR
A[Phase 1: Lag] --> B[Phase 2: Exponential]
B --> C[Phase 3: Stationary]

text
A1[Slow growth<br/>Adjustment] -.-> A
B1[Rapid growth<br/>Exponential-like] -.-> B
C1[Plateau<br/>N ≈ K] -.-> C

style A fill:#FFE4E1
style B fill:#98FB98
style C fill:#87CEEB
text

#### Phase 1: Lag Phase 🐌
- **Duration:** Early time period
- **Growth:** Slow, nearly flat
- **Reason:** Organisms adjusting to environment
- **Population:** Much smaller than $K$
- **Timescale:** Hours to days

#### Phase 2: Log/Exponential Phase 🚀
- **Duration:** Intermediate time
- **Growth:** Rapid, exponential-like
- **Reason:** Optimal conditions, resources abundant
- **Population:** $\frac{K}{10}$ to $\frac{K}{2}$
- **Timescale:** Days to weeks
- **Max growth at:** $N = \frac{K}{2}$ (inflection point)

#### Phase 3: Stationary Phase ⚖️
- **Duration:** Long-term
- **Growth:** Approaches zero
- **Reason:** Resources depleted, competition high
- **Population:** Approaches $K$
- **Equilibrium:** $N \approx K$
- **Timescale:** Weeks onward

### 📈 Graphical Representation

**Shape:** S-curve (sigmoid)

**Key Points:**
- **Start:** $N(0) = N_0$
- **Inflection:** $N = \frac{K}{2}$ (steepest slope)
- **Asymptote:** $N \to K$ as $t \to \infty$

### 🎯 Inflection Point Analysis

**Inflection point occurs at:**
$$N^* = \frac{K}{2}$$

**Maximum growth rate:**
$$\left.\frac{dN}{dt}\right|_{N=K/2} = \frac{rK}{4}$$

This is where population grows fastest!

### 📝 Example Problem

**Question:** A fish population in a lake has:
- Carrying capacity $K = 10,000$ fish
- Growth rate $r = 0.5$ per year
- Initial population $N_0 = 500$ fish

**a) What is the population after 5 years?**

**Solution:**
$$A = \frac{10000 - 500}{500} = 19$$

$$N(5) = \frac{10000}{1 + 19e^{-0.5 \times 5}} = \frac{10000}{1 + 19e^{-2.5}}$$

$$N(5) = \frac{10000}{1 + 19 \times 0.082} = \frac{10000}{2.56} = 3,906 \text{ fish}$$

**b) When does population reach 9,000 fish?**

**Solution:**
$$9000 = \frac{10000}{1 + 19e^{-0.5t}}$$

$$1 + 19e^{-0.5t} = \frac{10000}{9000} = 1.111$$

$$19e^{-0.5t} = 0.111$$

$$e^{-0.5t} = 0.00584$$

$$-0.5t = \ln(0.00584) = -5.14$$

$$t = 10.28 \text{ years}$$

### 🌍 Real-World Applications

| System | $K$ (Carrying Capacity) | Application |
|--------|-------------------------|-------------|
| 🐟 **Fish in lake** | Limited by food, space | Fisheries management |
| 🦌 **Deer in forest** | Limited by vegetation | Wildlife conservation |
| 🧫 **Bacteria in flask** | Limited by nutrients | Fermentation optimization |
| 🌱 **Plants in field** | Limited by space, light | Agriculture planning |
| 🎗️ **Tumor cells** | Limited by blood supply | Cancer treatment |

### ⚖️ Advantages & Limitations

**✅ Advantages:**
- More realistic than exponential
- Predicts equilibrium population
- Accounts for resource limitation
- Fits many biological datasets well
- Easy to understand and implement

**❌ Limitations:**
- Assumes constant $K$ (may vary seasonally)
- No time lags (response is immediate)
- Ignores age structure
- Assumes continuous reproduction
- No spatial heterogeneity

---

## 🐠 Von Bertalanffy Growth Model

**Concept:** Describes growth of individual organisms (especially fish) that approach an asymptotic maximum size.

### Mathematical Formulation

**Differential Equation:**
$$\frac{dL}{dt} = k(L_\infty - L)$$

**Analytical Solution:**
$$L(t) = L_\infty\left(1 - e^{-k(t-t_0)}\right)$$

**Parameters:**
- $L(t)$ = Length (or mass) at time $t$
- $L_\infty$ = Asymptotic maximum length
- $k$ = Growth coefficient (rate of approach to $L_\infty$)
- $t_0$ = Theoretical age at zero length (often set to 0)

### 📊 Characteristics

**Shape:** Asymmetric curve

**Key Features:**
- Fast initial growth (newborn)
- Growth rate decreases with size
- Asymptotically approaches $L_\infty$
- Never actually reaches $L_\infty$ (approaches forever)

### 🆚 Von Bertalanffy vs Logistic

| Feature | Logistic | Von Bertalanffy |
|---------|----------|-----------------|
| **Equation** | $\frac{dN}{dt} = rN(1-\frac{N}{K})$ | $\frac{dL}{dt} = k(L_\infty - L)$ |
| **Variable** | Population count | Individual size |
| **Curve Shape** | Symmetric S-curve | Asymmetric curve |
| **Inflection Point** | At $N = K/2$ | No clear inflection |
| **Initial Growth** | Slow (lag phase) | Fast (maximum at birth) |
| **Best For** | Populations | Individual organisms |
| **Applications** | Ecology, epidemiology | Fisheries, aquaculture |

### 🐟 Applications

**Fisheries Management:**
- Estimate fish age from length
- Determine growth rates
- Set size limits for harvesting
- Optimize aquaculture conditions

**Other Organisms:**
- Marine mammals (whales, seals)
- Reptiles (turtles, crocodiles)
- Large fish (tuna, sharks)

### 📝 Example

**Question:** A tuna has:
- $L_\infty = 200$ cm
- $k = 0.2$ per year
- $t_0 = 0$

What is its length at age 5 years?

**Solution:**
$$L(5) = 200\left(1 - e^{-0.2 \times 5}\right) = 200(1 - e^{-1})$$
$$L(5) = 200(1 - 0.368) = 200 \times 0.632 = 126.4 \text{ cm}$$

---

## 📉 Gompertz Growth Model

**Concept:** Models asymmetric S-shaped growth with slower deceleration phase. Commonly used for tumors and mortality studies.

### Mathematical Formulation

**Differential Equation:**
$$\frac{dN}{dt} = -rN\ln\left(\frac{N}{K}\right)$$

**Alternative Form:**
$$\frac{dN}{dt} = rN\ln\left(\frac{K}{N}\right)$$

**Parameters:**
- $N(t)$ = Population or size
- $r$ = Growth rate parameter
- $K$ = Asymptotic maximum (carrying capacity)
- $\ln$ = Natural logarithm

### 📊 Characteristics

**Shape:** Asymmetric S-curve

**Key Features:**
- Inflection point NOT at $K/2$
- Slower initial growth than logistic
- More gradual approach to $K$
- Better fits certain biological data

### 🎗️ Applications

| Application | Why Gompertz? | Example |
|-------------|---------------|---------|
| **Tumor Growth** | Matches cancer data better | Breast cancer progression |
| **Mortality Rates** | Human aging patterns | Life expectancy tables |
| **Cell Cultures** | Asymmetric growth phases | CHO cell lines |
| **Economic Growth** | Product adoption curves | Technology diffusion |

### 🆚 Gompertz vs Logistic

| Feature | Logistic | Gompertz |
|---------|----------|----------|
| **Symmetry** | Symmetric around inflection | Asymmetric |
| **Inflection Point** | At $N = K/2$ | At $N = K/e$ ≈ 0.37$K$ |
| **Early Growth** | Faster | Slower |
| **Late Growth** | Faster approach to $K$ | Slower approach to $K$ |
| **Tumor Fit** | Good | Better |

### 📝 Example

**Tumor Growth:** A tumor follows Gompertz growth with:
- $r = 0.05$ per day
- $K = 10^9$ cells

If current size is $N = 10^6$ cells, what is growth rate?

**Solution:**
$$\frac{dN}{dt} = 0.05 \times 10^6 \times \ln\left(\frac{10^9}{10^6}\right)$$
$$\frac{dN}{dt} = 0.05 \times 10^6 \times \ln(1000) = 0.05 \times 10^6 \times 6.91$$
$$\frac{dN}{dt} = 345,500 \text{ cells/day}$$

---

## 📊 Growth Models Summary Table

| Model | Equation | Shape | Inflection | Best For |
|-------|----------|-------|------------|----------|
| **Exponential** | $\frac{dN}{dt} = rN$ | J-curve | None | Unlimited growth, early phase |
| **Logistic** | $\frac{dN}{dt} = rN(1-\frac{N}{K})$ | Symmetric S | $K/2$ | Limited resources, populations |
| **Von Bertalanffy** | $\frac{dL}{dt} = k(L_\infty - L)$ | Asymmetric | None | Individual organism size |
| **Gompertz** | $\frac{dN}{dt} = -rN\ln(\frac{N}{K})$ | Asymmetric S | $K/e$ | Tumors, mortality, asymmetric growth |

---

# 6️⃣ Enzyme Kinetics & Substrate Constraints

Enzyme kinetics describes how enzymes catalyze reactions and how reaction rates depend on substrate availability.

graph LR
A[Substrate S] -->|k₁| B[Enzyme-Substrate Complex ES]
B -->|k₂| C[Product P + Enzyme E]
B -->|k₋₁| A

text
style A fill:#FFE4E1
style B fill:#98FB98
style C fill:#87CEEB
text

---

## 🧪 Substrate-Dependent Growth

### What is a Substrate? 🔬

**Definition:** Resource required for enzymatic reactions or organism growth

**Types:**
1. **Biochemical:** Glucose, amino acids, ATP
2. **Nutritional:** Nitrogen, phosphorus, carbon source
3. **Physical:** Oxygen, light, temperature
4. **Spatial:** Available space, surface area

### Why Substrate Limits Growth 📉

**Liebig's Law of the Minimum:**
> *"Growth is limited by the scarcest resource (substrate), not the total resources available."*

**Example:**
- If nitrogen is 10% of requirement but all else abundant
- Growth limited to 10% of potential
- Adding more carbon won't help!

---

## ⚗️ Michaelis-Menten Enzyme Kinetics

### 🧬 The Enzyme-Substrate Mechanism

**Reaction Scheme:**
$$E + S \underset{k_{-1}}{\overset{k_1}{\rightleftharpoons}} ES \overset{k_2}{\longrightarrow} E + P$$

**Steps:**
1. **Binding:** Enzyme ($E$) binds substrate ($S$) → Complex ($ES$)
2. **Catalysis:** Complex converts to product ($P$)
3. **Release:** Enzyme released, ready for next reaction

**Rate Constants:**
- $k_1$ = Forward binding rate
- $k_{-1}$ = Reverse binding rate (dissociation)
- $k_2$ = Catalytic rate (product formation)

### 📐 Michaelis-Menten Equation

**Reaction Velocity:**
$$v = \frac{V_{max}[S]}{K_m + [S]}$$

**Parameters:**
- $v$ = Reaction velocity (rate)
- $V_{max}$ = Maximum reaction velocity
- $[S]$ = Substrate concentration
- $K_m$ = Michaelis constant

### 🔑 Understanding $V_{max}$ and $K_m$

#### $V_{max}$ - Maximum Velocity ⚡

**Definition:** Reaction rate when enzyme is fully saturated with substrate

**Interpretation:**
- Plateau value on Michaelis-Menten curve
- Represents total enzyme capacity
- Proportional to enzyme concentration: $V_{max} = k_{cat}[E]_{total}$
- Units: concentration/time (e.g., μM/s, mM/min)

**What Determines $V_{max}$:**
- Amount of enzyme present
- Catalytic efficiency ($k_{cat}$ or turnover number)
- Temperature (higher = faster, up to denaturation)
- pH (optimal pH gives max activity)

#### $K_m$ - Michaelis Constant 🎯

**Definition:** Substrate concentration at which $v = \frac{V_{max}}{2}$

**Interpretation:**
- Measure of enzyme-substrate affinity
- **Low $K_m$** → High affinity (enzyme binds substrate tightly)
- **High $K_m$** → Low affinity (enzyme binds substrate weakly)
- Units: concentration (same as $[S]$)

**$K_m$ Values:**

| $K_m$ Range | Affinity | Example |
|-------------|----------|---------|
| < 10 μM | Very high | Hexokinase (glucose) |
| 10-100 μM | High | Most metabolic enzymes |
| 100 μM - 1 mM | Moderate | Carbonic anhydrase |
| > 1 mM | Low | Some biosynthetic enzymes |

### 📊 Michaelis-Menten Behavior

#### Low Substrate Concentration ($[S] \ll K_m$)

**Regime:** First-order kinetics

**Equation simplifies to:**
$$v \approx \frac{V_{max}[S]}{K_m}$$

**Characteristics:**
- Reaction rate proportional to $[S]$ (linear)
- Doubling substrate doubles rate
- **Rate-limiting:** Substrate availability

**Example:**
If $[S] = 0.1 K_m$:
$$v = \frac{V_{max} \times 0.1K_m}{K_m + 0.1K_m} = \frac{0.1V_{max}}{1.1} ≈ 0.09V_{max}$$

Only 9% of maximum rate!

#### Intermediate Substrate ($[S] \approx K_m$)

**Regime:** Mixed-order kinetics

**At $[S] = K_m$:**
$$v = \frac{V_{max} \times K_m}{K_m + K_m} = \frac{V_{max}}{2}$$

**Characteristics:**
- Half-maximum velocity
- Transition between first and zero order
- Most sensitive to changes in $[S]$

#### High Substrate Concentration ($[S] \gg K_m$)

**Regime:** Zero-order kinetics

**Equation simplifies to:**
$$v \approx V_{max}$$

**Characteristics:**
- Reaction rate constant (independent of $[S]$)
- Enzyme fully saturated
- **Rate-limiting:** Enzyme concentration
- Adding more substrate doesn't increase rate

**Example:**
If $[S] = 10 K_m$:
$$v = \frac{V_{max} \times 10K_m}{K_m + 10K_m} = \frac{10V_{max}}{11} ≈ 0.91V_{max}$$

91% of maximum rate!

### 📈 Graphical Representation

**Michaelis-Menten Curve:**

| $[S]$ | $v$ (fraction of $V_{max}$) |
|-------|----------------------------|
| 0 | 0 |
| $0.5 K_m$ | 0.33 $V_{max}$ |
| $K_m$ | 0.50 $V_{max}$ |
| $2 K_m$ | 0.67 $V_{max}$ |
| $5 K_m$ | 0.83 $V_{max}$ |
| $10 K_m$ | 0.91 $V_{max}$ |
| $\infty$ | $V_{max}$ |

**Key Features:**
- Rectangular hyperbola
- Steep initial slope (first-order region)
- Plateau at $V_{max}$ (zero-order region)
- $K_m$ is x-coordinate of half-max point

### 🧮 Assumptions of Michaelis-Menten

| Assumption | Explanation | Consequence if Violated |
|------------|-------------|------------------------|
| **Steady-state** | $[ES]$ constant | Model invalid for transient phase |
| **$[S] \gg [E]$** | Substrate excess | Free $[S]$ ≈ total $[S]$ |
| **Low product** | $[P]$ negligible | Reaction irreversible |
| **Single substrate** | No other substrates | Doesn't apply to multi-substrate |
| **No inhibitors** | No competitive/noncompetitive | Need modified equations |
| **Constant conditions** | pH, T constant | Parameters change otherwise |

### 📝 Example Problem

**Question:** An enzyme has:
- $V_{max} = 100$ μM/min
- $K_m = 20$ μM

What is the reaction velocity at:
a) $[S] = 5$ μM  
b) $[S] = 20$ μM  
c) $[S] = 100$ μM

**Solutions:**

**a) $[S] = 5$ μM:**
$$v = \frac{100 \times 5}{20 + 5} = \frac{500}{25} = 20 \text{ μM/min}$$

**b) $[S] = 20$ μM:**
$$v = \frac{100 \times 20}{20 + 20} = \frac{2000}{40} = 50 \text{ μM/min}$$

**c) $[S] = 100$ μM:**
$$v = \frac{100 \times 100}{20 + 100} = \frac{10000}{120} = 83.3 \text{ μM/min}$$

---

## 📏 Lineweaver-Burk Plot

### Purpose 🎯

Transform nonlinear Michaelis-Menten equation into linear form for easier parameter determination.

### 🧮 The Double Reciprocal Plot

**Lineweaver-Burk Equation:**
$$\frac{1}{v} = \frac{K_m}{V_{max}} \cdot \frac{1}{[S]} + \frac{1}{V_{max}}$$

**Linear Form:** $y = mx + b$

Where:
- $y = \frac{1}{v}$ (y-axis)
- $x = \frac{1}{[S]}$ (x-axis)
- Slope $m = \frac{K_m}{V_{max}}$
- Y-intercept $b = \frac{1}{V_{max}}$
- X-intercept $= -\frac{1}{K_m}$

### 📊 Extracting Parameters

**From Lineweaver-Burk Plot:**

graph LR
A[Y-intercept = 1/Vₘₐₓ] --> B[Calculate Vₘₐₓ]
C[X-intercept = -1/Kₘ] --> D[Calculate Kₘ]
E[Slope = Kₘ/Vₘₐₓ] --> F[Verify consistency]

text
style A fill:#FFE4E1
style C fill:#98FB98
style E fill:#87CEEB
text

**Step-by-Step:**

1. **Measure Y-intercept:**
   $$\text{Y-intercept} = \frac{1}{V_{max}}$$
   $$V_{max} = \frac{1}{\text{Y-intercept}}$$

2. **Measure X-intercept:**
   $$\text{X-intercept} = -\frac{1}{K_m}$$
   $$K_m = -\frac{1}{\text{X-intercept}}$$

3. **Calculate Slope:**
   $$\text{Slope} = \frac{K_m}{V_{max}}$$

### 📝 Example Problem

**Data:**

| $[S]$ (μM) | $v$ (μM/min) | $1/[S]$ (μM⁻¹) | $1/v$ (min/μM) |
|------------|--------------|----------------|----------------|
| 5 | 20 | 0.20 | 0.050 |
| 10 | 33 | 0.10 | 0.030 |
| 20 | 50 | 0.05 | 0.020 |
| 50 | 71 | 0.02 | 0.014 |
| 100 | 83 | 0.01 | 0.012 |

**Plot $1/v$ vs $1/[S]$:**

**From graph:**
- Y-intercept = 0.010 min/μM → $V_{max} = 100$ μM/min
- X-intercept = -0.05 μM⁻¹ → $K_m = 20$ μM

### ⚖️ Advantages & Disadvantages

**✅ Advantages:**
- Linear relationship (easier to fit)
- Easy visual parameter extraction
- Good for detecting enzyme inhibition types
- Historical importance

**❌ Disadvantages:**
- Transforms errors (gives unequal weight to data points)
- Emphasizes low $[S]$ data (often less accurate)
- Can be misleading if data poorly distributed
- Modern preference: Nonlinear regression (more accurate)

### 🚫 Types of Enzyme Inhibition (Lineweaver-Burk Analysis)

#### 1️⃣ Competitive Inhibition 🏁

**Mechanism:** Inhibitor competes with substrate for active site

**Effect:**
- $K_m$ increases (appears to have lower affinity)
- $V_{max}$ unchanged (can overcome with high $[S]$)

**Lineweaver-Burk:**
- Lines intersect on y-axis
- Slope increases with inhibitor

**Examples:** Malonate inhibits succinate dehydrogenase

#### 2️⃣ Non-competitive Inhibition 🚫

**Mechanism:** Inhibitor binds to different site (allosteric)

**Effect:**
- $K_m$ unchanged (affinity same)
- $V_{max}$ decreases (some enzyme inactivated)

**Lineweaver-Burk:**
- Lines intersect on x-axis
- Y-intercept increases with inhibitor

**Examples:** Heavy metals (Pb²⁺, Hg²⁺)

#### 3️⃣ Uncompetitive Inhibition 🔒

**Mechanism:** Inhibitor binds only to $ES$ complex

**Effect:**
- Both $K_m$ and $V_{max}$ decrease
- Ratio $V_{max}/K_m$ constant

**Lineweaver-Burk:**
- Parallel lines (same slope)
- Both intercepts change

**Less common in single-substrate reactions**

---

## 🌱 Substrate-Limited Growth (Monod Equation)

### Microbial Growth with Substrate Limitation

**Monod Equation:**
$$\mu = \mu_{max} \frac{S}{K_s + S}$$

**Parameters:**
- $\mu$ = Specific growth rate
- $\mu_{max}$ = Maximum specific growth rate
- $S$ = Substrate concentration
- $K_s$ = Half-saturation constant (analogous to $K_m$)

**Population Growth:**
$$\frac{dN}{dt} = \mu N = \mu_{max} \frac{S}{K_s + S} \cdot N$$

**Substrate Depletion:**
$$\frac{dS}{dt} = -\frac{1}{Y} \mu_{max} \frac{S}{K_s + S} \cdot N$$

Where $Y$ = yield coefficient (cells produced per unit substrate)

### 📝 Example: Bacterial Fermentation

**Setup:**
- $\mu_{max} = 0.5$ hr⁻¹
- $K_s = 0.1$ g/L
- $Y = 10^8$ cells/g
- Initial: $N_0 = 10^6$ cells/mL, $S_0 = 5$ g/L

**Questions:**
a) Initial growth rate?  
b) When does growth slow significantly?

**Solutions:**

**a) Initial growth rate:**
$$\mu(t=0) = 0.5 \times \frac{5}{0.1 + 5} = 0.5 \times \frac{5}{5.1} = 0.49 \text{ hr}^{-1}$$

Nearly maximum!

**b) Growth slows when $S \approx K_s = 0.1$ g/L**

Calculate time when substrate reaches this level using numerical integration.

---

## 📊 Enzyme Kinetics Summary

| Model | Equation | Application | Key Parameter |
|-------|----------|-------------|---------------|
| **Michaelis-Menten** | $v = \frac{V_{max}[S]}{K_m + [S]}$ | Enzyme reactions | $K_m$ (affinity) |
| **Lineweaver-Burk** | $\frac{1}{v} = \frac{K_m}{V_{max}} \frac{1}{[S]} + \frac{1}{V_{max}}$ | Parameter extraction | Intercepts |
| **Monod** | $\mu = \mu_{max}\frac{S}{K_s + S}$ | Microbial growth | $K_s$ (half-saturation) |

---

# 7️⃣ Population Interaction Models

Populations don't exist in isolation—they interact through predation, competition, mutualism, and other relationships.

graph TD
A[Population Interactions] --> B[🦊🐰 Predator-Prey]
A --> C[🌿🌿 Competition]
A --> D[🐝🌸 Mutualism]
A --> E[🦠🧍 Parasitism]

text
B --> F[Lotka-Volterra Predator-Prey]
C --> G[Lotka-Volterra Competition]

style B fill:#FFB6C1
style C fill:#98FB98
text

---

## 🦊🐰 Lotka-Volterra Predator-Prey Model

### 🎯 Concept & Context

**System:** Two interacting species
- **Predators** ($y$): Eat prey (e.g., foxes, wolves, sharks)
- **Prey** ($x$): Eaten by predators (e.g., rabbits, deer, fish)

**Question Answered:**  
How do predator and prey populations change over time? Do they reach equilibrium or oscillate?

### 🧮 Mathematical Equations

**Prey Population:**
$$\frac{dx}{dt} = \alpha x - \beta xy$$

**Predator Population:**
$$\frac{dy}{dt} = \delta xy - \gamma y$$

### 🔑 Parameters Explained

| Parameter | Meaning | Units | Typical Range |
|-----------|---------|-------|---------------|
| $x$ | Prey population | Number | 100-10,000 |
| $y$ | Predator population | Number | 10-1,000 |
| $\alpha$ | Prey birth rate | 1/time | 0.1-1.0 |
| $\beta$ | Predation rate | 1/(predator·time) | 0.001-0.01 |
| $\gamma$ | Predator death rate | 1/time | 0.05-0.5 |
| $\delta$ | Conversion efficiency | 1/(prey·time) | 0.0001-0.001 |

### 📊 Understanding the Equations

#### Prey Dynamics 🐰

$$\frac{dx}{dt} = \underbrace{\alpha x}_{\text{Birth}} - \underbrace{\beta xy}_{\text{Predation}}$$

**Term 1: $\alpha x$ (Exponential Growth)**
- Prey reproduce naturally
- Growth independent of predators
- Positive contribution
- Would lead to exponential growth if alone

**Term 2: $-\beta xy$ (Predation Loss)**
- Prey eaten by predators
- Proportional to **both** populations
- If either $x$ or $y$ is zero → no predation
- Negative contribution (removes prey)

**Interpretation:**
- When predators few → prey increase rapidly
- When predators many → prey decrease rapidly
- Prey can't escape extinction without reproduction

#### Predator Dynamics 🦊

$$\frac{dy}{dt} = \underbrace{\delta xy}_{\text{Growth from feeding}} - \underbrace{\gamma y}_{\text{Starvation}}$$

**Term 1: $\delta xy$ (Growth from Predation)**
- Predators increase by eating prey
- Proportional to encounters ($xy$)
- More prey → more predators can survive
- Positive contribution

**Term 2: $-\gamma y$ (Natural Death)**
- Predators die from starvation/old age
- Constant rate (doesn't depend on prey)
- Without prey, predators go extinct
- Negative contribution

**Interpretation:**
- When prey abundant → predators thrive
- When prey scarce → predators starve
- Predators always have baseline mortality

### 🔄 Oscillatory Dynamics

**Key Result:** Populations oscillate in cycles!

graph TD
A[High Prey
Low Predators] --> B[Predators Increase
Prey Still High]
B --> C[High Predators
Prey Decline]
C --> D[Predators Starve
Prey Still Low]
D --> E[Low Predators
Prey Recover]
E --> A

text
style A fill:#90EE90
style B fill:#FFD700
style C fill:#FF6B6B
style D fill:#FFA07A
style E fill:#87CEEB
text

### 📈 The Predator-Prey Cycle

**Phase 1: Prey Abundant, Predators Increasing** 🐰⬆️🦊⬆️
- Plenty of food for predators
- Predator population grows
- Prey still numerous but starting to decline

**Phase 2: Predators Peak, Prey Declining** 🐰⬇️🦊⬆️
- Maximum predator numbers
- Heavy predation pressure
- Prey population crashes

**Phase 3: Prey Scarce, Predators Starving** 🐰⬇️🦊⬇️
- Insufficient prey to sustain predators
- Predator population declines
- Prey at minimum

**Phase 4: Predators Low, Prey Recovering** 🐰⬆️🦊⬇️
- Reduced predation pressure
- Prey population rebounds
- Few predators remain

**Phase 5: Cycle Repeats** 🔄

### ⏱️ Time Lag Phenomenon

**Observation:** Predator population peaks **lag behind** prey peaks

**Why?**
- Takes time for predators to reproduce after prey increase
- Typical lag: Quarter cycle (90°)
- Biological delay from feeding → reproduction

**Example:**
- Prey peak at month 0, 12, 24, ...
- Predator peak at month 3, 15, 27, ...
- Delay = 3 months

### 🎯 Equilibrium Analysis

**Equilibrium:** Both populations constant ($\frac{dx}{dt} = 0$ and $\frac{dy}{dt} = 0$)

**Two Equilibria:**

#### 1️⃣ Trivial Equilibrium
$$(x^*, y^*) = (0, 0)$$

Both species extinct (biologically unrealistic, mathematically unstable)

#### 2️⃣ Non-Trivial Equilibrium
$$x^* = \frac{\gamma}{\delta}, \quad y^* = \frac{\alpha}{\beta}$$

**Interpretation:**
- Equilibrium exists at specific population values
- System doesn't settle at equilibrium—orbits around it
- **Neutral stability:** Oscillations persist indefinitely
- Closed orbits in phase space

### 📊 Phase Space Analysis

**Phase Portrait:** Plot $y$ (predators) vs $x$ (prey)

**Key Features:**
- Closed curves (elliptical orbits)
- Counterclockwise direction
- All trajectories circle equilibrium point
- Initial conditions determine orbit size

**Quadrant Analysis:**

| Region | Prey Trend | Predator Trend | What Happens? |
|--------|------------|----------------|---------------|
| High $x$, Low $y$ | Increasing | Increasing | Prey still growing, predators start increasing |
| High $x$, High $y$ | Decreasing | Increasing | Predators eating prey, still growing |
| Low $x$, High $y$ | Decreasing | Decreasing | Both declining (starvation) |
| Low $x$, Low $y$ | Increasing | Decreasing | Prey recovering, predators still dying |

### 📝 Example Problem

**Setup:**
- Rabbits (prey): $\alpha = 0.5$, initially $x_0 = 100$
- Foxes (predators): $\gamma = 0.2$, initially $y_0 = 10$
- Interaction: $\beta = 0.01$, $\delta = 0.001$

**Find equilibrium:**

$$x^* = \frac{\gamma}{\delta} = \frac{0.2}{0.001} = 200 \text{ rabbits}$$
$$y^* = \frac{\alpha}{\beta} = \frac{0.5}{0.01} = 50 \text{ foxes}$$

**Interpretation:**
- System oscillates around 200 rabbits and 50 foxes
- Starting conditions (100, 10) below equilibrium
- Populations will cycle through these values

### 🌍 Real-World Examples

| Ecosystem | Predator | Prey | Observation |
|-----------|----------|------|-------------|
| 🇨🇦 **Canadian Forest** | Lynx | Snowshoe Hare | 10-year cycles (Hudson Bay data) |
| 🌊 **Marine** | Orca | Seal | Multi-year oscillations |
| 🦟 **Microscopic** | Didinium | Paramecium | Lab-confirmed cycles |
| 🌲 **Forest** | Wolf | Deer | Isle Royale study |
| 🦅 **Savanna** | Hawk | Mouse | Seasonal variations |

### ⚠️ Model Limitations

| Limitation | Reality | Extension Needed |
|------------|---------|------------------|
| **No carrying capacity** | Prey can't grow infinitely | Add logistic term for prey |
| **No refuge** | All prey equally vulnerable | Add functional response |
| **Homogeneous space** | No spatial structure | Add diffusion/migration |
| **Constant parameters** | Seasons, climate change | Time-varying parameters |
| **Two species only** | Complex food webs | Multi-species models |
| **Deterministic** | Stochasticity matters (small populations) | Stochastic models |

### 🔧 Model Extensions

#### Modified Lotka-Volterra with Carrying Capacity

**Prey equation with logistic growth:**
$$\frac{dx}{dt} = \alpha x\left(1 - \frac{x}{K}\right) - \beta xy$$

**Effect:**
- Prey has maximum population $K$
- More realistic for resource-limited prey
- Can stabilize oscillations (damped cycles)

#### Functional Response Models

**Type II (Holling):**
$$\frac{dx}{dt} = \alpha x - \frac{\beta xy}{1 + h\beta x}$$

Where $h$ = handling time per prey

**Effect:**
- Predator satiation (can't eat infinitely fast)
- More realistic predation at high prey density

---

## 🌿🌿 Lotka-Volterra Competition Model

### 🎯 Concept & Context

**System:** Two species competing for the same limiting resources

**Competition Types:**
- 🍃 **Plants** competing for sunlight, water, nutrients
- 🦠 **Bacteria** competing for glucose in culture
- 🐦 **Birds** competing for nesting sites
- 🦁 **Predators** competing for same prey

**Question:** Can both species coexist, or will one drive the other extinct?

### 🧮 Mathematical Equations

**Species 1:**
$$\frac{dN_1}{dt} = r_1N_1\left(\frac{K_1 - N_1 - \alpha_{12}N_2}{K_1}\right)$$

**Species 2:**
$$\frac{dN_2}{dt} = r_2N_2\left(\frac{K_2 - N_2 - \alpha_{21}N_1}{K_2}\right)$$

### 🔑 Parameters Explained

| Parameter | Meaning | Interpretation |
|-----------|---------|----------------|
| $N_1, N_2$ | Population sizes | Number of individuals |
| $r_1, r_2$ | Intrinsic growth rates | Growth without competition |
| $K_1, K_2$ | Carrying capacities | Max population alone |
| $\alpha_{12}$ | Effect of species 2 on species 1 | Competition coefficient |
| $\alpha_{21}$ | Effect of species 1 on species 2 | Competition coefficient |

### 💡 Understanding Competition Coefficients

**$\alpha_{12}$ - How much species 2 impacts species 1:**

$$\alpha_{12} = \frac{\text{Effect of 1 individual of species 2}}{\text{Effect of 1 individual of species 1}}$$

**Examples:**

| $\alpha_{12}$ Value | Meaning |
|---------------------|---------|
| $\alpha_{12} = 0$ | No competition (species 2 doesn't affect species 1) |
| $\alpha_{12} = 0.5$ | One species 2 individual = 0.5 species 1 individuals |
| $\alpha_{12} = 1$ | Equal competitive effect |
| $\alpha_{12} = 2$ | Species 2 twice as competitive |

**Asymmetry:** Usually $\alpha_{12} \neq \alpha_{21}$ (species have different competitive abilities)

### 📊 Breaking Down the Equations

**Species 1 Growth:**
$$\frac{dN_1}{dt} = r_1N_1\underbrace{\left(\frac{K_1 - N_1 - \alpha_{12}N_2}{K_1}\right)}_{\text{Available carrying capacity}}$$

**Numerator Analysis:**
- $K_1$ = Total carrying capacity for species 1
- $-N_1$ = Intraspecific competition (self-crowding)
- $-\alpha_{12}N_2$ = Interspecific competition (from species 2)

**When $N_2 = 0$ (species 2 absent):**
$$\frac{dN_1}{dt} = r_1N_1\left(\frac{K_1 - N_1}{K_1}\right)$$
Simple logistic growth!

**When $N_2 > 0$ (species 2 present):**
- Available resources reduced by $\alpha_{12}N_2$
- Species 1 feels competition from species 2
- Effective carrying capacity lowered

### 🎭 Four Possible Outcomes

The fate of competing species depends on competition coefficients and carrying capacities.

graph TD
A[Competition Outcomes] --> B[Outcome 1:
Species 1 Wins]
A --> C[Outcome 2:
Species 2 Wins]
A --> D[Outcome 3:
Stable Coexistence]
A --> E[Outcome 4:
Unstable Coexistence]

text
B --> F[Competitive Exclusion]
C --> F
D --> G[Both Survive]
E --> H[Winner Depends on<br/>Initial Conditions]

style B fill:#FFB6C1
style C fill:#FF6B6B
style D fill:#90EE90
style E fill:#FFD700
text

#### 🏆 Outcome 1: Species 1 Wins (Competitive Exclusion)

**Conditions:**
$$\frac{K_1}{K_2} > \alpha_{12} \quad \text{AND} \quad \frac{K_2}{K_1} < \alpha_{21}$$

**English Translation:**
- Species 1's carrying capacity (relative to species 2) is large
- Species 1 inhibits itself less than species 2 inhibits it
- Species 1 is the superior competitor

**Result:**
- $N_1^* = K_1$ (species 1 at carrying capacity)
- $N_2^* = 0$ (species 2 extinct)

**Example:** Invasive plant outcompetes native species

#### 🏆 Outcome 2: Species 2 Wins (Competitive Exclusion)

**Conditions:**
$$\frac{K_2}{K_1} > \alpha_{21} \quad \text{AND} \quad \frac{K_1}{K_2} < \alpha_{12}$$

**Result:**
- $N_1^* = 0$ (species 1 extinct)
- $N_2^* = K_2$ (species 2 at carrying capacity)

**Example:** Superior predator eliminates inferior competitor

#### 🤝 Outcome 3: Stable Coexistence

**Conditions:**
$$\frac{K_1}{K_2} > \alpha_{12} \quad \text{AND} \quad \frac{K_2}{K_1} > \alpha_{21}$$

**English Translation:**
- Each species inhibits **itself** more than it inhibits the other
- Intraspecific competition > Interspecific competition
- Niche differentiation exists

**Result:**
- Both species survive at stable equilibrium:
$$N_1^* = \frac{K_1 - \alpha_{12}K_2}{1 - \alpha_{12}\alpha_{21}}$$
$$N_2^* = \frac{K_2 - \alpha_{21}K_1}{1 - \alpha_{12}\alpha_{21}}$$

**Example:** 
- Two plant species using different soil layers
- Birds nesting at different heights
- Bacteria using different nutrient sources

#### ⚠️ Outcome 4: Unstable Coexistence (Priority Effect)

**Conditions:**
$$\frac{K_1}{K_2} < \alpha_{12} \quad \text{AND} \quad \frac{K_2}{K_1} < \alpha_{21}$$

**English Translation:**
- Each species inhibits the other more than itself
- Interspecific competition > Intraspecific competition
- Strong mutual interference

**Result:**
- Unstable equilibrium exists mathematically
- But any perturbation leads to competitive exclusion
- **Winner depends on initial population sizes**
- "Founder effect" - whoever arrives first wins

**Example:**
- Two similar species introduced to new habitat
- Whichever establishes first excludes the other

### 📊 Outcome Summary Table

| Outcome | Conditions | $N_1^*$ | $N_2^*$ | Biological Meaning |
|---------|------------|---------|---------|-------------------|
| **1. Species 1 Wins** | $K_1/K_2 > \alpha_{12}$, $K_2/K_1 < \alpha_{21}$ | $K_1$ | $0$ | Species 1 superior competitor |
| **2. Species 2 Wins** | $K_1/K_2 < \alpha_{12}$, $K_2/K_1 > \alpha_{21}$ | $0$ | $K_2$ | Species 2 superior competitor |
| **3. Stable Coexist** | $K_1/K_2 > \alpha_{12}$, $K_2/K_1 > \alpha_{21}$ | $>0$ | $>0$ | Niche differentiation allows both |
| **4. Unstable** | $K_1/K_2 < \alpha_{12}$, $K_2/K_1 < \alpha_{21}$ | $K_1$ or $0$ | $0$ or $K_2$ | Priority effect determines winner |

### 📝 Example Problem

**Setup:** Two bacterial strains competing in a chemostat:
- Species 1: $r_1 = 0.5$ hr⁻¹, $K_1 = 10^8$ cells/mL
- Species 2: $r_2 = 0.6$ hr⁻¹, $K_2 = 8 \times 10^7$ cells/mL
- Competition: $\alpha_{12} = 0.8$, $\alpha_{21} = 1.2$

**Question:** What is the outcome?

**Solution:**

Check conditions for each outcome:

**Check 1:** $\frac{K_1}{K_2} = \frac{10^8}{8 \times 10^7} = 1.25$

**Check 2:** $\frac{K_1}{K_2} = 1.25 > \alpha_{12} = 0.8$ ✅

**Check 3:** $\frac{K_2}{K_1} = \frac{8 \times 10^7}{10^8} = 0.8$

**Check 4:** $\frac{K_2}{K_1} = 0.8 < \alpha_{21} = 1.2$ ✅

**Conclusion:** Outcome 1 - **Species 1 Wins** (Competitive Exclusion)

Species 2 will go extinct, species 1 reaches $K_1 = 10^8$ cells/mL

### 🌍 Real-World Competition Examples

| System | Species 1 | Species 2 | Outcome | Mechanism |
|--------|-----------|-----------|---------|-----------|
| 🌱 **Darwin's Finches** | Large beak | Small beak | Coexistence | Seed size partitioning |
| 🦠 **Bacteria** | *E. coli* | *S. aureus* | Exclusion | Antibiotic production |
| 🌲 **Trees** | Oak | Maple | Coexistence | Light/water niche separation |
| 🐜 **Ants** | Invasive | Native | Exclusion | Resource monopolization |
| 🐟 **Fish** | Bass | Bluegill | Coexistence | Different feeding depths |

### 🧬 Competitive Exclusion Principle

> **Gause's Principle:** "Complete competitors cannot coexist. Two species cannot occupy the same ecological niche indefinitely."

**Implications:**
- ✅ Coexistence requires niche differentiation
- ✅ Similar species evolve to use different resources
- ✅ Character displacement (divergent evolution)
- ✅ Temporal or spatial partitioning

**Niche Differentiation Mechanisms:**

| Type | Example | Result |
|------|---------|--------|
| 🍽️ **Resource Partitioning** | Different food sizes | Coexistence |
| 🕐 **Temporal Separation** | Active different times | Coexistence |
| 🌍 **Spatial Separation** | Different habitats | Coexistence |
| 🎯 **Character Displacement** | Beak size divergence | Reduced competition |

---

## 🐝🌸 Mutualism Models (Extension)

### 🤝 What is Mutualism?

**Definition:** Both species benefit from interaction (+/+ relationship)

**Examples:**
- 🐝 Bees pollinate flowers (bee gets nectar, flower reproduces)
- 🦠 Gut bacteria aid digestion (bacteria get food, host gets nutrients)
- 🐠 Cleaner fish remove parasites (fish get food, host gets clean)
- 🍄 Mycorrhizal fungi help plants (fungi get sugars, plants get minerals)

### 🧮 Mutualism Equations

**Species 1 (benefits from Species 2):**
$$\frac{dN_1}{dt} = r_1N_1\left(\frac{K_1 + \alpha_{12}N_2 - N_1}{K_1}\right)$$

**Species 2 (benefits from Species 1):**
$$\frac{dN_2}{dt} = r_2N_2\left(\frac{K_2 + \alpha_{21}N_1 - N_2}{K_2}\right)$$

**Note:** $\alpha_{12}, \alpha_{21} > 0$ (positive effect!)

**Key Difference from Competition:**
- Competition: $-\alpha N$ (negative term)
- Mutualism: $+\alpha N$ (positive term)

**Outcomes:**
- Both populations increase beyond solo carrying capacity
- Effective carrying capacities: $K_1 + \alpha_{12}N_2$ and $K_2 + \alpha_{21}N_1$
- Stable coexistence at higher equilibrium

---

# 8️⃣ Oscillations & Biological Rhythms

Biological systems exhibit rhythmic behaviors at multiple timescales, from millisecond neural firing to annual migrations.

graph TD
A[Biological Oscillations] --> B[⚡ Fast
Milliseconds-Seconds]
A --> C[⏱️ Medium
Minutes-Hours]
A --> D[📅 Slow
Days-Years]

text
B --> E[Action potentials<br/>Heart beats]
C --> F[Glycolysis<br/>Calcium waves]
D --> G[Circadian rhythms<br/>Seasonal cycles]

style B fill:#FFB6C1
style C fill:#98FB98
style D fill:#87CEEB
text

---

## 🧪 Glycolytic Oscillations

### 🔋 What is Glycolysis?

**Definition:** Central metabolic pathway converting glucose to pyruvate, producing ATP

**Overall Reaction:**
$$\text{Glucose} + 2\text{NAD}^+ + 2\text{ADP} + 2P_i \rightarrow 2\text{Pyruvate} + 2\text{NADH} + 2\text{ATP} + 2\text{H}_2\text{O}$$

**Key Features:**
- 🔟 10 enzymatic steps
- ⚡ Occurs in cytoplasm
- 🔄 Produces 2 ATP (net) per glucose
- 🧬 Universal to all cells
- 🕐 Completes in seconds to minutes

### 🌊 Why Does Glycolysis Oscillate?

**Mechanism:** Feedback loops + Time delays = Oscillations

graph TD
A[Glucose Input] --> B[PFK Enzyme
Phosphofructokinase]
B --> C[Glycolytic Intermediates]
C --> D[ATP Production]
D -->|Negative Feedback| B
C -->|Positive Feedback| B
D --> E[NADH Production]

text
style B fill:#FFD700
style D fill:#FF6B6B
style E fill:#87CEEB
text

#### 🔄 Feedback Mechanisms

**1️⃣ Positive Feedback (+)**
- ADP activates PFK (phosphofructokinase)
- Low ATP → high ADP → PFK activated
- Amplifies glycolytic flux
- Creates acceleration

**2️⃣ Negative Feedback (−)**
- ATP inhibits PFK
- High ATP → PFK inhibited
- Slows glycolytic rate
- Creates damping

**3️⃣ Time Delays (⏱️)**
- Enzyme synthesis takes time
- Product accumulation not instantaneous
- Diffusion delays
- Enables oscillations (not just steady state)

### 🔬 Key Regulatory Enzyme: PFK

**Phosphofructokinase (PFK):**
- Rate-limiting enzyme in glycolysis
- Catalyzes: Fructose-6-P → Fructose-1,6-bisphosphate
- Allosteric regulation (multiple binding sites)

**Regulation:**

| Molecule | Effect | Reason |
|----------|--------|--------|
| 🔴 **ATP** | Inhibits PFK | High energy signal |
| 🔴 **Citrate** | Inhibits PFK | TCA cycle full |
| 🟢 **ADP** | Activates PFK | Low energy signal |
| 🟢 **AMP** | Activates PFK | Energy depletion |
| 🟢 **Fructose-2,6-bisP** | Activates PFK | Feedforward activation |

### 📊 Oscillation Dynamics

#### Phase 1: Low ATP, High PFK Activity 🟢
- PFK fully active (no ATP inhibition)
- Glucose rapidly metabolized
- Glycolytic intermediates accumulate
- NADH builds up
- ATP starts rising

**Duration:** 1-2 minutes

#### Phase 2: High ATP, PFK Inhibition 🔴
- ATP accumulates and inhibits PFK
- Glycolytic rate slows dramatically
- NADH gradually reoxidized
- ATP consumed by cellular processes
- ATP levels decline

**Duration:** 1-2 minutes

#### Phase 3: Recovery, Cycle Repeats 🔄
- ATP drops below inhibition threshold
- PFK reactivated
- Glycolysis accelerates
- Return to Phase 1

**Period:** 3-7 minutes (varies by organism and conditions)

### 📈 Observable Oscillations

**What Can We Measure?**

| Variable | Measurement Method | Oscillation Amplitude |
|----------|-------------------|----------------------|
| **NADH** | Fluorescence (340 nm) | ±20-30% |
| **ATP** | Bioluminescence (luciferase) | ±10-20% |
| **pH** | Fluorescent indicators | ±0.1-0.2 units |
| **O₂ consumption** | Oxygen electrode | ±15-25% |

**Typical Trace:**
- Sinusoidal or sawtooth waveform
- Regular period (3-7 min)
- Amplitude stable in steady conditions
- Synchronized across cell population

### 🧬 Synchronization in Cell Populations

**Individual Cells:**
- Each cell oscillates with slightly different phase
- Period varies by ±10% between cells
- Isolated cells maintain oscillations

**Population Synchronization:**
- Cells communicate via **acetaldehyde** (volatile compound)
- Diffuses between cells
- Couples oscillators
- Population beats in unison

**Mathematical Model (Kuramoto Model):**
$$\frac{d\theta_i}{dt} = \omega_i + \frac{K}{N}\sum_{j=1}^{N}\sin(\theta_j - \theta_i)$$

Where:
- $\theta_i$ = Phase of cell $i$
- $\omega_i$ = Natural frequency of cell $i$
- $K$ = Coupling strength
- $N$ = Number of cells

### 🎯 Biological Significance

**Why Oscillations Matter:**

#### 1️⃣ Metabolic Coordination 🔄
- Synchronizes glycolysis with TCA cycle
- Coordinates ATP production/consumption
- Couples to respiratory chain
- Optimizes energy efficiency

#### 2️⃣ Cell Communication 📡
- Population-level rhythm emerges
- Coordinate metabolism across tissue
- Timing signal for other processes
- Example: Yeast culture synchrony

#### 3️⃣ Energy Efficiency ⚡
- Prevents wasteful futile cycles
- Optimizes substrate utilization
- Reduces byproduct accumulation
- Improves ATP yield

#### 4️⃣ Temporal Organization 🕐
- Acts as cellular clock
- Times cell cycle events
- Coordinates with calcium oscillations
- Influences circadian rhythms

### 📝 Mathematical Model of Glycolytic Oscillations

**Simplified 2-Variable Model:**

$$\frac{dS}{dt} = v_0 - k_1S\frac{P^2}{1+P^2}$$

$$\frac{dP}{dt} = k_1S\frac{P^2}{1+P^2} - k_2P$$

Where:
- $S$ = Substrate (ADP) concentration
- $P$ = Product (ATP) concentration
- $v_0$ = Glucose input rate
- $k_1$ = PFK activity coefficient
- $k_2$ = ATP consumption rate

**Key Feature:** $\frac{P^2}{1+P^2}$ creates positive feedback (autocatalysis)

---

## ⏰ Circadian Rhythms

### 🌅 What are Circadian Rhythms?

**Definition:** ~24-hour biological cycles that regulate physiology and behavior

**Etymology:** *circa* (about) + *dies* (day)

**Examples:**
- 😴 Sleep-wake cycles
- 🌡️ Body temperature fluctuations
- 💊 Hormone secretion (cortisol, melatonin)
- 🧬 Gene expression patterns
- 📊 Metabolism rates

### 🧬 Molecular Mechanism

**Core Clock Genes:**

graph TD
A[CLOCK/BMAL1
Activator Complex] --> B[Per/Cry Genes]
B --> C[PER/CRY Proteins]
C --> D[Accumulation in Cytoplasm]
D --> E[Enter Nucleus]
E -->|Negative Feedback| A
E --> F[Inhibit Transcription]
F --> G[PER/CRY Degradation]
G --> A

text
style A fill:#FFD700
style C fill:#98FB98
style E fill:#FF6B6B
text

**Transcription-Translation Feedback Loop (TTFL):**

1. **Activation Phase (Day):**
   - CLOCK/BMAL1 activates *Per* and *Cry* genes
   - PER and CRY proteins synthesized
   - Takes several hours

2. **Accumulation Phase (Evening):**
   - PER/CRY accumulate in cytoplasm
   - Form complexes
   - Phosphorylated (modified)

3. **Inhibition Phase (Night):**
   - PER/CRY enter nucleus
   - Inhibit CLOCK/BMAL1
   - Transcription stops

4. **Degradation Phase (Late Night):**
   - PER/CRY degraded by proteases
   - Cycle resets
   - Morning: CLOCK/BMAL1 active again

**Time Delays:**
- Transcription: 1-2 hours
- Translation: 1-2 hours
- Protein accumulation: 4-6 hours
- Nuclear entry: 2-3 hours
- Degradation: 4-6 hours
- **Total:** ~24 hours!

### 📊 Mathematical Model (Simplified)

**Goodwin Oscillator (1965):**

$$\frac{dM}{dt} = \frac{v_s}{1 + P^n} - k_mM$$

$$\frac{dP}{dt} = k_sM - k_pP$$

Where:
- $M$ = mRNA concentration
- $P$ = Protein concentration
- $v_s$ = Max transcription rate
- $k_m$ = mRNA degradation rate
- $k_s$ = Translation rate
- $k_p$ = Protein degradation rate
- $n$ = Hill coefficient (cooperativity)

**Key:** $\frac{1}{1+P^n}$ creates negative feedback (protein inhibits own transcription)

### 🌍 Entrainment to Environment

**Free-Running Period:** ~24.2 hours (varies by individual)

**Entrainment:** Synchronization to external cues (zeitgebers)

**Primary Zeitgeber:** 💡 **Light**
- Detected by retinal photoreceptors
- Signal to suprachiasmatic nucleus (SCN) in brain
- Resets clock phase daily
- Advances or delays rhythm

**Other Zeitgebers:**
- 🍽️ Food timing
- 🌡️ Temperature cycles
- 👥 Social interactions
- 💊 Exercise timing

### 📝 Example: Jet Lag

**Scenario:** Travel from New York to Tokyo (13-hour time difference)

**Day 1:**
- Internal clock: 3 AM (sleepy)
- Tokyo time: 4 PM (afternoon)
- Mismatch causes fatigue, confusion

**Recovery:**
- Clock shifts ~1 hour/day
- Full adjustment: ~13 days
- Eastward travel harder (phase advance)
- Light exposure accelerates adaptation

---

## 🔬 General Requirements for Oscillations

### 🧮 Mathematical Prerequisites

**For a system to oscillate, it typically needs:**

#### 1️⃣ Nonlinearity ⚡

**Why:** Linear systems converge to steady state or diverge—they don't oscillate

**Examples of Nonlinearity:**
- Hill functions: $\frac{V_{max}S^n}{K^n + S^n}$
- Product terms: $xy$ (predator-prey)
- Saturation: $\frac{S}{K+S}$

**Linear System (No Oscillation):**
$$\frac{dx}{dt} = ax + by$$
$$\frac{dy}{dt} = cx + dy$$

Exponential growth/decay only (no cycles)

#### 2️⃣ Feedback Loops 🔄

**Essential Ingredients:**

| Feedback Type | Effect | Example |
|---------------|--------|---------|
| **Negative Feedback** | Opposes change, stabilizing | ATP inhibits PFK |
| **Positive Feedback** | Amplifies change, destabilizing | ADP activates PFK |
| **Both Required** | Creates oscillations | Glycolysis |

**Negative Feedback Alone:** Damped approach to equilibrium (no sustained oscillations)

**Positive Feedback Alone:** Runaway growth or bistability (no oscillations)

**Both Together:** Sustained oscillations!

#### 3️⃣ Time Delays ⏱️

**Why Critical:**
- Instantaneous feedback → damping
- Delayed feedback → oscillations

**Types of Delays:**
- Transcription time (minutes)
- Translation time (minutes)
- Diffusion time (seconds-minutes)
- Enzyme synthesis (minutes-hours)

**Example:**
- PFK inhibited by ATP
- But ATP production takes time
- By the time ATP accumulates, glycolysis already accelerated
- Overshoot → Oscillation

#### 4️⃣ Appropriate Parameters 🎛️

**Not all parameter values produce oscillations!**

**Bifurcation:** System behavior changes qualitatively as parameter varies

**Parameter Space:**
- Some regions → Steady state
- Other regions → Oscillations
- Other regions → Chaos

**Example:** Predator-prey model
- Low $\beta$ (weak predation) → Prey grows, predators starve
- Optimal $\beta$ → Oscillations
- High $\beta$ (strong predation) → Both extinct

### 📊 Minimum Complexity for Oscillations

**Theorem:** Need at least **2 coupled variables** for autonomous oscillations

**1-Variable System:**
$$\frac{dx}{dt} = f(x)$$

**Cannot oscillate** (always converges or diverges monotonically)

**2-Variable System:**
$$\frac{dx}{dt} = f(x, y)$$
$$\frac{dy}{dt} = g(x, y)$$

**Can oscillate** if conditions met (nonlinearity, feedback, delays)

**Example:** Predator-prey, glycolysis (ADP-ATP)

---

## 🔢 Examples of Biological Oscillations

### Summary Table

| Oscillation | Period | Mechanism | Function |
|-------------|--------|-----------|----------|
| **Action Potentials** | 1-10 ms | Na⁺/K⁺ channel dynamics | Neural signaling |
| **Heartbeat** | 0.6-1 s | Pacemaker cells | Blood circulation |
| **Calcium Waves** | 10 s - 5 min | Ca²⁺ release/uptake | Cell signaling |
| **Glycolysis** | 3-7 min | PFK feedback | Metabolic regulation |
| **Cell Cycle** | 10-24 hrs | Cyclin-CDK oscillations | Cell division |
| **Circadian** | ~24 hrs | Gene regulatory loops | Daily physiology |
| **Menstrual Cycle** | 28 days | Hormone feedback | Reproduction |
| **Predator-Prey** | Months-Years | Population interactions | Ecosystem dynamics |
| **Seasonal** | 1 year | Photoperiod changes | Migration, hibernation |

### 📈 Oscillation Characteristics

**Amplitude:** Peak-to-trough difference

**Period:** Time for one complete cycle

**Frequency:** $f = \frac{1}{\text{Period}}$

**Phase:** Position within cycle

**Coherence:** How regular (high coherence = precise period)

---

# 9️⃣ Mathematical Techniques & Methods

## 📐 Differentiation

### 🔢 First-Order Differentiation

**Definition:** Rate of change of a function with respect to a variable

**Notation:**
$$f'(x) \quad \text{or} \quad \frac{dy}{dx} \quad \text{or} \quad \frac{df}{dx}$$

**Geometric Interpretation:** Slope of tangent line at point $x$

**Physical Interpretation:** Instantaneous velocity (if $y$ = position)

### 🧮 Common Derivatives

| Function | Derivative | Example |
|----------|------------|---------|
| $f(x) = c$ | $f'(x) = 0$ | $\frac{d}{dx}(5) = 0$ |
| $f(x) = x^n$ | $f'(x) = nx^{n-1}$ | $\frac{d}{dx}(x^3) = 3x^2$ |
| $f(x) = e^x$ | $f'(x) = e^x$ | $\frac{d}{dx}(e^x) = e^x$ |
| $f(x) = \ln(x)$ | $f'(x) = \frac{1}{x}$ | $\frac{d}{dx}(\ln x) = \frac{1}{x}$ |
| $f(x) = \sin(x)$ | $f'(x) = \cos(x)$ | $\frac{d}{dx}(\sin x) = \cos x$ |
| $f(x) = \cos(x)$ | $f'(x) = -\sin(x)$ | $\frac{d}{dx}(\cos x) = -\sin x$ |

### 📏 Differentiation Rules

**Product Rule:**
$$\frac{d}{dx}[f(x)g(x)] = f'(x)g(x) + f(x)g'(x)$$

**Quotient Rule:**
$$\frac{d}{dx}\left[\frac{f(x)}{g(x)}\right] = \frac{f'(x)g(x) - f(x)g'(x)}{[g(x)]^2}$$

**Chain Rule:**
$$\frac{d}{dx}[f(g(x))] = f'(g(x)) \cdot g'(x)$$

**Example:** $\frac{d}{dx}[(x^2 + 1)^3]$

Let $u = x^2 + 1$, then:
$$\frac{d}{dx}[u^3] = 3u^2 \cdot \frac{du}{dx} = 3(x^2+1)^2 \cdot 2x = 6x(x^2+1)^2$$

### 📊 Biological Interpretation

**In Population Dynamics:**
$$\frac{dN}{dt} > 0 \implies \text{Population increasing}$$
$$\frac{dN}{dt} = 0 \implies \text{Population steady (equilibrium)}$$
$$\frac{dN}{dt} < 0 \implies \text{Population decreasing}$$

**Example:** Logistic growth
$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)$$

- When $N < K$: $\frac{dN}{dt} > 0$ (growth)
- When $N = K$: $\frac{dN}{dt} = 0$ (equilibrium)
- When $N > K$: $\frac{dN}{dt} < 0$ (decline)

---

### 🔢 Second-Order Differentiation

**Definition:** Derivative of the derivative (rate of change of rate of change)

**Notation:**
$$f''(x) \quad \text{or} \quad \frac{d^2y}{dx^2}$$

**Physical Interpretation:** Acceleration (if $y$ = position)

**Geometric Interpretation:** Curvature (concavity) of function

### 📊 Concavity Analysis

| Condition | Shape | Meaning |
|-----------|-------|---------|
| $f''(x) > 0$ | Concave up (∪) | Increasing at increasing rate |
| $f''(x) = 0$ | Inflection point | Change in concavity |
| $f''(x) < 0$ | Concave down (∩) | Increasing at decreasing rate |

### 🎯 Critical Points

**First Derivative Test (Extrema):**
- $f'(x) = 0$ → Critical point (potential max/min)
- $f''(x) > 0$ → Local minimum
- $f''(x) < 0$ → Local maximum
- $f''(x) = 0$ → Inconclusive (test higher derivatives)

**Second Derivative Test (Inflection Points):**
- $f''(x) = 0$ and $f''$ changes sign → Inflection point
- Curve changes from concave up to concave down (or vice versa)

### 📝 Example: Logistic Growth Analysis

**Equation:**
$$N(t) = \frac{K}{1 + Ae^{-rt}}$$

**First Derivative (Growth Rate):**
$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right)$$

**Second Derivative (Acceleration):**
$$\frac{d^2N}{dt^2} = r\frac{dN}{dt}\left(1 - \frac{2N}{K}\right)$$

**Inflection Point (Maximum Growth Rate):**
Set $\frac{d^2N}{dt^2} = 0$:
$$1 - \frac{2N}{K} = 0 \implies N = \frac{K}{2}$$

**Interpretation:** Population grows fastest at half carrying capacity!

---

### 🔄 Implicit Differentiation

**When to Use:**
- Equation not solved for $y$
- Cannot easily isolate $y$
- Relationship given implicitly: $F(x,y) = 0$

**Procedure:**
1. Differentiate both sides with respect to $x$
2. Apply chain rule to terms with $y$ (multiply by $\frac{dy}{dx}$)
3. Collect all $\frac{dy}{dx}$ terms
4. Solve for $\frac{dy}{dx}$

### 📝 Example: Circle

**Equation:** $x^2 + y^2 = 25$

**Find:** $\frac{dy}{dx}$

**Solution:**

Step 1: Differentiate both sides
$$\frac{d}{dx}(x^2) + \frac{d}{dx}(y^2) = \frac{d}{dx}(25)$$

Step 2: Apply chain rule
$$2x + 2y\frac{dy}{dx} = 0$$

Step 3: Solve for $\frac{dy}{dx}$
$$2y\frac{dy}{dx} = -2x$$
$$\frac{dy}{dx} = -\frac{x}{y}$$

**Interpretation:** Slope of circle at point $(x, y)$ depends on both coordinates

### 🧬 Biological Example: Allometric Scaling

**Relationship:** $y = ax^b$ (e.g., metabolic rate vs body mass)

**Implicit Form:** $\ln(y) = \ln(a) + b\ln(x)$

**Differentiate:**
$$\frac{1}{y}\frac{dy}{dx} = \frac{b}{x}$$

$$\frac{dy}{dx} = \frac{by}{x}$$

**Interpretation:** Proportional change in $y$ relative to proportional change in $x$

---

## 🧮 Numerical Methods

### 📊 Euler Method

**Purpose:** Numerically solve differential equations when analytical solution impossible

**Problem Setup:**
$$\frac{dy}{dt} = f(t, y), \quad y(t_0) = y_0$$

**Goal:** Find $y(t)$ for $t > t_0$

### 🔢 Euler Algorithm

**Core Idea:** Use tangent line to approximate curve

**Formula:**
$$y_{n+1} = y_n + h \cdot f(t_n, y_n)$$

**Parameters:**
- $h$ = Step size (time interval)
- $y_n$ = Solution at time $t_n$
- $f(t_n, y_n)$ = Slope at current point
- $y_{n+1}$ = Approximate solution at next time step

**Geometric Interpretation:**
1. At point $(t_n, y_n)$, calculate slope $f(t_n, y_n)$
2. Move along tangent line for distance $h$
3. New point becomes next approximation
4. Repeat

### 📋 Step-by-Step Procedure

**Input:**
- Differential equation: $\frac{dy}{dt} = f(t, y)$
- Initial condition: $y(t_0) = y_0$
- Time interval: $t_0$ to $t_{final}$
- Step size: $h$

**Algorithm:**
Initialize: t = t₀, y = y₀

While t < t_final:
a. Calculate slope: k = f(t, y)
b. Update y: y_new = y + h × k
c. Update t: t_new = t + h
d. Store (t_new, y_new)
e. Set t = t_new, y = y_new

Return time series and solution arrays

text

### 📝 Example: Exponential Growth

**Problem:** Solve $\frac{dN}{dt} = 0.5N$ with $N(0) = 10$

**Parameters:** $h = 0.5$, solve from $t=0$ to $t=2$

**Analytical Solution:** $N(t) = 10e^{0.5t}$

**Euler Method:**

| Step | $t_n$ | $N_n$ | $\frac{dN}{dt} = 0.5N_n$ | $N_{n+1} = N_n + 0.5 \times \frac{dN}{dt}$ |
|------|-------|-------|--------------------------|-------------------------------------------|
| 0 | 0.0 | 10.000 | 5.000 | 12.500 |
| 1 | 0.5 | 12.500 | 6.250 | 15.625 |
| 2 | 1.0 | 15.625 | 7.813 | 19.531 |
| 3 | 1.5 | 19.531 | 9.766 | 24.414 |
| 4 | 2.0 | 24.414 | - | - |

**Comparison at $t=2$:**
- Exact: $N(2) = 10e^1 = 27.183$
- Euler: $N(2) = 24.414$
- Error: $\frac{27.183 - 24.414}{27.183} \times 100\% = 10.2\%$

### ⚠️ Error Analysis

**Local Truncation Error (per step):**
$$E_{local} = O(h^2)$$

Proportional to $h^2$ (from Taylor series)

**Global Truncation Error (cumulative):**
$$E_{global} = O(h)$$

Proportional to $h$ (accumulates over $\frac{T}{h}$ steps)

**Reducing Error:**
- Halve step size → Halve global error
- But doubles computation time
- Trade-off: accuracy vs speed

### 🎯 Choosing Step Size

| Step Size | Accuracy | Computation Time | Use When |
|-----------|----------|------------------|----------|
| Large ($h \geq 1$) | Poor | Fast | Quick approximation |
| Medium ($h \approx 0.1$) | Moderate | Moderate | Typical applications |
| Small ($h \leq 0.01$) | Good | Slow | High precision needed |
| Adaptive | Optimal | Variable | Modern implementations |

### 🚀 Better Methods (Higher-Order)

**Euler Limitations:**
- First-order accuracy only
- Large errors for stiff equations
- Inefficient for high precision

**Improved Methods:**

| Method | Order | Error | Evaluations/Step | Use Case |
|--------|-------|-------|------------------|----------|
| **Euler** | 1st | $O(h)$ | 1 | Simple, educational |
| **Midpoint** | 2nd | $O(h^2)$ | 2 | Better than Euler |
| **RK4** | 4th | $O(h^4)$ | 4 | Standard choice |
| **Adaptive RK** | Variable | Controlled | Variable | Production code |

### 🧮 Runge-Kutta 4 (RK4) Algorithm

**Most Popular Method:** 4th-order accuracy with reasonable computation

**Formula:**
$$y_{n+1} = y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)$$

Where:
$$k_1 = f(t_n, y_n)$$
$$k_2 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_1\right)$$
$$k_3 = f\left(t_n + \frac{h}{2}, y_n + \frac{h}{2}k_2\right)$$
$$k_4 = f(t_n + h, y_n + hk_3)$$

**Advantages:**
- Much more accurate than Euler
- Still straightforward to implement
- Industry standard for ODE solving

### 💻 Python Implementation

**Using SciPy (Recommended):**

import numpy as np
from scipy.integrate import odeint, solve_ivp
import matplotlib.pyplot as plt

Define ODE: dN/dt = rN(1 - N/K)
def logistic(N, t, r, K):
dNdt = r * N * (1 - N/K)
return dNdt

Parameters
r = 0.5 # Growth rate
K = 1000 # Carrying capacity
N0 = 10 # Initial population

Time span
t = np.linspace(0, 20, 200)

Solve using odeint
solution = odeint(logistic, N0, t, args=(r, K))

Plot
plt.figure(figsize=(10, 6))
plt.plot(t, solution, 'b-', linewidth=2, label='Population')
plt.axhline(K, color='r', linestyle='--', label=f'Carrying Capacity (K={K})')
plt.xlabel('Time', fontsize=12)
plt.ylabel('Population Size', fontsize=12)
plt.title('Logistic Growth Model', fontsize=14, fontweight='bold')
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()

text

**Manual Euler Implementation:**

def euler_method(f, y0, t0, tf, h):
"""
Euler method for solving dy/dt = f(t, y)

text
Parameters:
- f: function defining dy/dt
- y0: initial condition
- t0: start time
- tf: end time
- h: step size

Returns:
- t_values: array of time points
- y_values: array of solution values
"""
t_values = [t0]
y_values = [y0]

t = t0
y = y0

while t < tf:
    slope = f(t, y)
    y_new = y + h * slope
    t_new = t + h
    
    t_values.append(t_new)
    y_values.append(y_new)
    
    t = t_new
    y = y_new

return np.array(t_values), np.array(y_values)
Example: dN/dt = 0.5*N
def exponential_growth(t, N):
return 0.5 * N

t_euler, N_euler = euler_method(exponential_growth, 10, 0, 2, 0.1)

Compare with analytical solution
t_exact = np.linspace(0, 2, 100)
N_exact = 10 * np.exp(0.5 * t_exact)

plt.figure(figsize=(10, 6))
plt.plot(t_exact, N_exact, 'b-', linewidth=2, label='Exact Solution')
plt.plot(t_euler, N_euler, 'ro-', markersize=6, label='Euler Method')
plt.xlabel('Time')
plt.ylabel('Population')
plt.title('Euler Method vs Exact Solution')
plt.legend()
plt.grid(True, alpha=0.3)
plt.show()

text

---

## 🎲 Monte Carlo Simulations

### 🎯 What is Monte Carlo?

**Definition:** Computational method using repeated random sampling to solve problems

**Core Principle:** Use randomness to explore system behavior

**Name Origin:** Monte Carlo casino in Monaco (gambling/randomness)

### 🔍 When to Use Monte Carlo

**Ideal Scenarios:**

| Problem Type | Why Monte Carlo? | Example |
|--------------|------------------|---------|
| **High-dimensional** | Analytical solution intractable | Protein folding (thousands of atoms) |
| **Stochastic systems** | Inherent randomness | Genetic drift, molecular collisions |
| **Complex interactions** | Too many variables | Ecosystem models |
| **Uncertainty quantification** | Need probability distributions | Drug efficacy trials |
| **Optimization** | Large parameter space | Evolutionary algorithms |

### 🧮 Monte Carlo Algorithm

**General Procedure:**

graph TD
A[1. Define Problem] --> B[2. Specify Input Distributions]
B --> C[3. Generate Random Samples]
C --> D[4. Run Simulation]
D --> E[5. Record Outcome]
E --> F{Enough
Iterations?}
F -->|No| C
F -->|Yes| G[6. Analyze Statistics]
G --> H[7. Report Results]

text
style A fill:#FFE4E1
style C fill:#98FB98
style G fill:#87CEEB
text

**Detailed Steps:**

1. **Define Problem & Variables**
   - Identify input parameters
   - Specify output of interest
   - Set number of iterations (N)

2. **Specify Probability Distributions**
   - Normal: $\mathcal{N}(\mu, \sigma^2)$
   - Uniform: $U(a, b)$
   - Poisson: $\text{Pois}(\lambda)$
   - Exponential: $\text{Exp}(\lambda)$

3. **Generate Random Samples**
   - Use random number generator
   - Sample from specified distributions
   - Create parameter set for this iteration

4. **Run Simulation**
   - Execute model with random parameters
   - Calculate output

5. **Record Results**
   - Store outcome in array
   - Repeat steps 3-5 for N iterations

6. **Statistical Analysis**
   - Calculate mean: $\bar{x} = \frac{1}{N}\sum_{i=1}^{N}x_i$
   - Standard deviation: $s = \sqrt{\frac{1}{N-1}\sum_{i=1}^{N}(x_i - \bar{x})^2}$
   - Percentiles: 5th, 50th (median), 95th
   - Create histograms

7. **Report Uncertainty**
   - Mean ± confidence interval
   - Probability distributions
   - Risk assessment

### 📝 Example: Population Genetic Drift

**Scenario:** Small population (N=50) with two alleles (A and a)

**Question:** What happens to allele frequency over generations?

**Parameters:**
- Population size: N = 50
- Initial frequency of A: p₀ = 0.5
- Generations: 100
- Simulations: 1000

**Python Implementation:**

import numpy as np
import matplotlib.pyplot as plt

def genetic_drift(N, p0, generations, num_sims):
"""
Simulate genetic drift in finite population

text
Parameters:
- N: Population size
- p0: Initial allele frequency
- generations: Number of generations
- num_sims: Number of simulation runs

Returns:
- trajectories: Array of allele frequency trajectories
"""
trajectories = np.zeros((num_sims, generations + 1))
trajectories[:, 0] = p0  # Initial frequency

for sim in range(num_sims):
    p = p0
    for gen in range(1, generations + 1):
        # Number of A alleles in next generation (binomial sampling)
        num_A = np.random.binomial(2 * N, p)
        p = num_A / (2 * N)
        trajectories[sim, gen] = p
        
        # Check for fixation or loss
        if p == 0 or p == 1:
            trajectories[sim, gen:] = p
            break

return trajectories
Run simulation
N = 50
p0 = 0.5
generations = 100
num_sims = 1000

trajectories = genetic_drift(N, p0, generations, num_sims)

Plot results
plt.figure(figsize=(14, 6))

Individual trajectories (first 50)
plt.subplot(1, 2, 1)
for i in range(50):
plt.plot(trajectories[i, :], alpha=0.3, linewidth=0.5)
plt.xlabel('Generation', fontsize=12)
plt.ylabel('Allele Frequency (p)', fontsize=12)
plt.title('Individual Trajectories', fontsize=14, fontweight='bold')
plt.axhline(0.5, color='r', linestyle='--', linewidth=2, label='Initial p')
plt.legend()
plt.grid(True, alpha=0.3)

Histogram at final generation
plt.subplot(1, 2, 2)
final_frequencies = trajectories[:, -1]
plt.hist(final_frequencies, bins=30, edgecolor='black', alpha=0.7)
plt.xlabel('Final Allele Frequency', fontsize=12)
plt.ylabel('Number of Simulations', fontsize=12)
plt.title('Distribution of Final Frequencies', fontsize=14, fontweight='bold')
plt.axvline(0.5, color='r', linestyle='--', linewidth=2, label='Initial p')
plt.legend()
plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()

Calculate statistics
fixation_A = np.sum(final_frequencies == 1) / num_sims * 100
loss_A = np.sum(final_frequencies == 0) / num_sims * 100
polymorphic = 100 - fixation_A - loss_A

print(f"After {generations} generations:")
print(f" Allele A fixed (p=1): {fixation_A:.1f}%")
print(f" Allele A lost (p=0): {loss_A:.1f}%")
print(f" Still polymorphic: {polymorphic:.1f}%")

text

**Expected Output:**
After 100 generations:
Allele A fixed (p=1): 48.2%
Allele A lost (p=0): 48.9%
Still polymorphic: 2.9%

text

**Interpretation:**
- Random drift causes allele frequencies to wander
- Eventually leads to fixation (p=1) or loss (p=0)
- Equal probability for each outcome (started at p=0.5)
- Smaller populations → faster drift

### 🧬 Example: Drug Efficacy with Uncertainty

**Scenario:** New drug with uncertain efficacy and side effects

**Parameters (with uncertainty):**
- Efficacy: Normal(0.7, 0.1) - mean 70%, std 10%
- Side effect rate: Beta(2, 8) - average 20%
- Cost: Uniform(50, 150) dollars

**Question:** What is expected benefit-cost ratio?

**Python Implementation:**

import numpy as np
import matplotlib.pyplot as plt
from scipy import stats

def drug_trial_simulation(num_patients, num_sims):
"""
Simulate drug trial with uncertain parameters
"""
results = []

text
for sim in range(num_sims):
    # Sample uncertain parameters
    efficacy = np.random.normal(0.7, 0.1)
    efficacy = np.clip(efficacy, 0, 1)  # Keep in[1]
    
    side_effect_rate = np.random.beta(2, 8)
    
    cost = np.random.uniform(50, 150)
    
    # Simulate patient outcomes
    cured = np.random.binomial(num_patients, efficacy)
    side_effects = np.random.binomial(num_patients, side_effect_rate)
    
    # Calculate benefit (arbitrary units)
    benefit = cured * 100 - side_effects * 30
    total_cost = cost * num_patients
    
    benefit_cost_ratio = benefit / total_cost
    
    results.append({
        'efficacy': efficacy,
        'side_effect_rate': side_effect_rate,
        'cost': cost,
        'cured': cured,
        'side_effects': side_effects,
        'benefit_cost_ratio': benefit_cost_ratio
    })

return results
Run simulation
num_patients = 100
num_sims = 10000

results = drug_trial_simulation(num_patients, num_sims)

Extract data
efficacies = [r['efficacy'] for r in results]
ratios = [r['benefit_cost_ratio'] for r in results]

Statistical analysis
mean_ratio = np.mean(ratios)
std_ratio = np.std(ratios)
ci_95 = stats.t.interval(0.95, len(ratios)-1,
loc=mean_ratio,
scale=stats.sem(ratios))

print(f"Benefit-Cost Ratio:")
print(f" Mean: {mean_ratio:.3f}")
print(f" Std Dev: {std_ratio:.3f}")
print(f" 95% CI: ({ci_95:.3f}, {ci_95:.3f})")​
print(f" Probability positive: {np.mean(np.array(ratios) > 0)*100:.1f}%")

Visualization
plt.figure(figsize=(12, 5))

plt.subplot(1, 2, 1)
plt.hist(efficacies, bins=50, alpha=0.7, edgecolor='black')
plt.xlabel('Efficacy', fontsize=12)
plt.ylabel('Frequency', fontsize=12)
plt.title('Distribution of Drug Efficacy', fontsize=14, fontweight='bold')
plt.axvline(np.mean(efficacies), color='r', linestyle='--',
linewidth=2, label=f'Mean = {np.mean(efficacies):.2f}')
plt.legend()
plt.grid(True, alpha=0.3)

plt.subplot(1, 2, 2)
plt.hist(ratios, bins=50, alpha=0.7, edgecolor='black')
plt.xlabel('Benefit-Cost Ratio', fontsize=12)
plt.ylabel('Frequency', fontsize=12)
plt.title('Distribution of Benefit-Cost Ratio', fontsize=14, fontweight='bold')
plt.axvline(mean_ratio, color='r', linestyle='--',
linewidth=2, label=f'Mean = {mean_ratio:.2f}')
plt.axvline(0, color='black', linestyle='-', linewidth=2, label='Break-even')
plt.legend()
plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()

text

### 🎯 Advantages of Monte Carlo

✅ **Versatile:** Works for almost any problem
✅ **Intuitive:** Mimics real-world randomness
✅ **Parallelizable:** Simulations independent
✅ **Handles complexity:** No analytical solution needed
✅ **Quantifies uncertainty:** Natural output is distribution

### ⚠️ Limitations of Monte Carlo

❌ **Computationally expensive:** Needs many iterations
❌ **Slow convergence:** Error $\propto \frac{1}{\sqrt{N}}$
❌ **Random number quality:** Results depend on RNG
❌ **Curse of dimensionality:** High-dimensional spaces problematic
❌ **No insight into mechanism:** Black box approach

### 📊 How Many Simulations?

**Rule of Thumb:**

| Precision Desired | Minimum Simulations |
|-------------------|---------------------|
| Rough estimate | 100 - 1,000 |
| Moderate precision | 10,000 - 100,000 |
| High precision | 100,000 - 1,000,000 |
| Publication quality | 1,000,000+ |

**Error Decreases as:** $\text{Error} \propto \frac{1}{\sqrt{N}}$

To halve error → need 4× simulations!

---

# 🔟 Practical Applications

## 🦠 Epidemiology: SIR Model

### 📊 SIR Compartmental Model

**Concept:** Track disease spread through population compartments

**Compartments:**
- **S (Susceptible):** Can catch disease
- **I (Infected):** Currently sick, can transmit
- **R (Recovered):** Immune, can't catch or transmit

graph LR
A[S
Susceptible] -->|Infection Rate β| B[I
Infected]
B -->|Recovery Rate γ| C[R
Recovered]

text
style A fill:#98FB98
style B fill:#FF6B6B
style C fill:#87CEEB
text

### 🧮 SIR Equations

$$\frac{dS}{dt} = -\beta SI$$

$$\frac{dI}{dt} = \beta SI - \gamma I$$

$$\frac{dR}{dt} = \gamma I$$

**Parameters:**
- $\beta$ = Transmission rate (contacts × probability of transmission)
- $\gamma$ = Recovery rate (1/infection duration)
- $N = S + I + R$ = Total population (constant)

**Conservation:** $\frac{d}{dt}(S + I + R) = 0$ (no births/deaths)

### 🔑 Key Concept: Basic Reproduction Number

**$R_0$ (R-naught):**
$$R_0 = \frac{\beta S_0}{\gamma}$$

**Interpretation:** Average number of secondary infections from one infected individual

| $R_0$ Value | Meaning | Outcome |
|-------------|---------|---------|
| $R_0 < 1$ | Each infected infects <1 person | Epidemic dies out |
| $R_0 = 1$ | Each infected infects 1 person | Endemic equilibrium |
| $R_0 > 1$ | Each infected infects >1 person | Epidemic spreads |

**Examples:**
- Measles: $R_0 \approx 12-18$ (highly contagious)
- COVID-19: $R_0 \approx 2-3$ (moderate)
- Ebola: $R_0 \approx 1.5-2.5$ (lower, but severe)
- Seasonal flu: $R_0 \approx 1.3$ (low)

### 📝 Example: COVID-19 Outbreak

**Parameters:**
- Population: $N = 10,000$
- Initial infected: $I_0 = 10$
- $\beta = 0.0005$ (contacts/day)
- $\gamma = 0.1$ (recovery in 10 days)

**Calculate $R_0$:**
$$R_0 = \frac{\beta S_0}{\gamma} = \frac{0.0005 \times 9990}{0.1} = 4.995 \approx 5$$

**Interpretation:** Each infected person infects ~5 others → Epidemic will spread rapidly!

**Python Simulation:**

import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

def sir_model(y, t, beta, gamma, N):
S, I, R = y
dSdt = -beta * S * I / N
dIdt = beta * S * I / N - gamma * I
dRdt = gamma * I
return [dSdt, dIdt, dRdt]

Parameters
N = 10000
I0 = 10
R0 = 0
S0 = N - I0 - R0
beta = 0.5
gamma = 0.1

Initial conditions
y0 = [S0, I0, R0]

Time vector (days)
t = np.linspace(0, 200, 200)

Solve ODE
solution = odeint(sir_model, y0, t, args=(beta, gamma, N))
S, I, R = solution.T

Plot
plt.figure(figsize=(12, 6))
plt.plot(t, S, 'b-', linewidth=2, label='Susceptible')
plt.plot(t, I, 'r-', linewidth=2, label='Infected')
plt.plot(t, R, 'g-', linewidth=2, label='Recovered')
plt.xlabel('Time (days)', fontsize=12)
plt.ylabel('Number of Individuals', fontsize=12)
plt.title(f'SIR Model (R₀ = {beta/gamma:.2f})', fontsize=14, fontweight='bold')
plt.legend(fontsize=11)
plt.grid(True, alpha=0.3)
plt.tight_layout()
plt.show()

Find peak infection
peak_day = np.argmax(I)
peak_infected = I[peak_day]
print(f"Peak infection: {peak_infected:.0f} people on day {peak_day}")
print(f"Total infected: {R[-1]:.0f} people ({R[-1]/N*100:.1f}% of population)")

text

### 💉 Intervention Strategies

**Goal:** Reduce $R_0$ below 1

**Methods:**

| Intervention | Effect on Parameters | $R_0$ Reduction |
|--------------|----------------------|-----------------|
| **Social Distancing** | Reduces $\beta$ (fewer contacts) | $R_0 \to R_0/2$ |
| **Masks** | Reduces $\beta$ (lower transmission) | $R_0 \to 0.7R_0$ |
| **Quarantine** | Removes $I$ from population | Variable |
| **Vaccination** | Reduces $S_0$ (fewer susceptible) | $R_0 \to (1-p)R_0$ |
| **Treatment** | Increases $\gamma$ (faster recovery) | $R_0 \to R_0(\gamma_{old}/\gamma_{new})$ |

**Herd Immunity Threshold:**
$$p_c = 1 - \frac{1}{R_0}$$

Fraction of population that must be immune to stop spread

**Example:** If $R_0 = 5$:
$$p_c = 1 - \frac{1}{5} = 0.8 = 80\%$$

Need 80% immune for herd immunity!

---

## 🎗️ Cancer Growth Modeling

### 📈 Tumor Growth Dynamics

**Challenge:** Tumors grow in complex patterns influenced by nutrients, space, immune system

**Common Models:**

#### 1️⃣ Exponential Growth (Early Stage)

$$\frac{dN}{dt} = rN$$

**Valid when:** Tumor small, resources abundant, no space constraints

#### 2️⃣ Gompertz Model (Avascular Phase)

$$\frac{dN}{dt} = -rN\ln\left(\frac{N}{K}\right)$$

**Best fit for:** Solid tumors without blood supply (< 2mm diameter)

**Characteristics:**
- Asymmetric S-curve
- Growth slows as tumor grows (nutrient diffusion limits)
- Approaches carrying capacity $K$

#### 3️⃣ Logistic + Therapy

$$\frac{dN}{dt} = rN\left(1 - \frac{N}{K}\right) - dN$$

Where $d$ = treatment-induced death rate

**Applications:** Chemotherapy, radiotherapy modeling

### 📝 Example: Chemotherapy Scheduling

**Scenario:** Breast cancer tumor with chemotherapy

**Parameters:**
- Initial tumor size: $N_0 = 10^6$ cells
- Growth rate: $r = 0.05$ per day
- Carrying capacity: $K = 10^{10}$ cells
- Chemo death rate: $d = 0.3$ per day (during treatment)
- Treatment cycles: 7 days on, 14 days off

**Python Simulation:**

import numpy as np
from scipy.integrate import odeint
import matplotlib.pyplot as plt

def tumor_model(N, t, r, K, d, treatment_schedule):
"""
Tumor growth with chemotherapy
"""
# Check if currently in treatment
day = int(t) % 21 # 21-day cycle
in_treatment = day < 7 # First 7 days = treatment

text
death_rate = d if in_treatment else 0

dNdt = r * N * (1 - N/K) - death_rate * N
return dNdt
Parameters
N0 = 1e6
r = 0.05
K = 1e10
d = 0.3

Time (days)
t = np.linspace(0, 300, 3000)

Solve
solution = odeint(tumor_model, N0, t, args=(r, K, d, None))
N = solution.flatten()

Plot
plt.figure(figsize=(14, 6))

plt.subplot(1, 2, 1)
plt.semilogy(t, N, 'b-', linewidth=2)
plt.axhline(K, color='r', linestyle='--', linewidth=2, label=f'Carrying Capacity')

Shade treatment periods
for cycle in range(int(t[-1]/21) + 1):
start = cycle * 21
end = start + 7
plt.axvspan(start, end, alpha=0.2, color='red')

plt.xlabel('Time (days)', fontsize=12)
plt.ylabel('Tumor Size (cells, log scale)', fontsize=12)
plt.title('Tumor Growth with Chemotherapy Cycles', fontsize=14, fontweight='bold')
plt.legend()
plt.grid(True, alpha=0.3, which='both')

plt.subplot(1, 2, 2)
plt.plot(t, N, 'b-', linewidth=2)
plt.xlabel('Time (days)', fontsize=12)
plt.ylabel('Tumor Size (cells)', fontsize=12)
plt.title('Linear Scale', fontsize=14, fontweight='bold')
plt.grid(True, alpha=0.3)

plt.tight_layout()
plt.show()

text

### 💊 Optimal Treatment Strategies

**Goal:** Minimize tumor size while managing toxicity

**Approaches:**

| Strategy | Description | Pros/Cons |
|----------|-------------|-----------|
| **Maximum Tolerated Dose (MTD)** | Highest safe dose continuously | Fast kill, high toxicity |
| **Metronomic** | Low dose continuously | Less toxic, prevents resistance |
| **Adaptive** | Adjust based on tumor response | Personalized, complex |
| **Intermittent** | Cycles of treatment + rest | Balances efficacy and recovery |

---

## 🌾 Agriculture: Crop Growth Models

### 🌱 Plant Growth with Resource Limitation

**Factors Affecting Growth:**
- 💧 Water availability
- ☀️ Light intensity
- 🌡️ Temperature
- 🧪 Nutrients (N, P, K)
- 💨 CO₂ concentration

**Monod-Type Growth:**
$$\mu = \mu_{max} \frac{N}{K_N + N} \cdot \frac{W}{K_W + W} \cdot f(T) \cdot f(L)$$

Where:
- $N$ = Nutrient concentration
- $W$ = Water availability
- $f(T)$ = Temperature function
- $f(L)$ = Light function

### 📊 Yield Optimization

**Question:** What combination of fertilizer and irrigation maximizes yield?

**Approach:** Use model to predict yield under different scenarios

**Monte Carlo for Uncertainty:**
- Weather variability
- Pest outbreaks
- Market price fluctuations

---

# 1️⃣1️⃣ Advanced Topics

## 🌀 Chaos Theory in Biological Systems

### 🦋 What is Chaos?

**Definition:** Deterministic systems exhibiting extreme sensitivity to initial conditions

**Key Features:**
- Deterministic (no randomness in equations)
- Unpredictable long-term (small changes → big differences)
- Bounded (doesn't go to infinity)
- Non-periodic (never exactly repeats)

### 📊 Logistic Map (Discrete Chaos)

**Equation:**
$$x_{n+1} = rx_n(1 - x_n)$$

**Behavior depends on $r$:**

| $r$ Range | Behavior | Example |
|-----------|----------|---------|
| $0 < r < 1$ | Extinction ($x \to 0$) | Population dies |
| $1 < r < 3$ | Stable equilibrium | Converges to fixed point |
| $3 < r < 3.57$ | Periodic oscillations | 2, 4, 8, ... cycles |
| $r > 3.57$ | Chaos | Unpredictable |

**Biological Example:** Insect populations with discrete generations

### 🌊 Strange Attractors

**Lorenz Attractor:**
- Weather model by Edward Lorenz (1963)
- Three coupled differential equations
- Butterfly-shaped attractor
- Origin of "butterfly effect"

**Biological Examples:**
- Heart rate variability
- Neural firing patterns
- Population cycles

---

## 🧬 Systems Biology Approaches

### 🔗 Network Modeling

**Types of Biological Networks:**

graph TD
A[Biological Networks] --> B[Gene Regulatory Networks]
A --> C[Metabolic Networks]
A --> D[Protein Interaction Networks]
A --> E[Neural Networks]

text
B --> F[Transcription factors → Genes]
C --> G[Enzymes → Metabolites]
D --> H[Protein-protein binding]
E --> I[Neurons → Synapses]

style A fill:#FFD700
style B fill:#FFB6C1
style C fill:#98FB98
style D fill:#87CEEB
style E fill:#DDA0DD
text

### 📊 Graph Theory in Biology

**Network Properties:**

| Property | Definition | Biological Meaning |
|----------|------------|-------------------|
| **Degree** | Number of connections per node | Hub proteins/genes |
| **Clustering** | How interconnected neighbors are | Functional modules |
| **Path Length** | Average distance between nodes | Information flow speed |
| **Centrality** | Importance of node | Essential genes/proteins |

**Scale-Free Networks:**
- Few highly connected hubs
- Many low-connectivity nodes
- Robust to random failures
- Vulnerable to targeted attacks

**Example:** Gene regulatory networks often scale-free

---

## 🧠 Neural Network Modeling

### ⚡ Hodgkin-Huxley Model

**Describes:** Action potential generation in neurons

**Equations:**
$$C_m\frac{dV}{dt} = I - \bar{g}_Na m^3h(V - E_{Na}) - \bar{g}_K n^4(V - E_K) - \bar{g}_L(V - E_L)$$

Plus gating variable equations for $m, h, n$

**Complexity:** 4 coupled nonlinear ODEs

**Result:** Reproduces action potential waveform

---

# 1️⃣2️⃣ Quick Reference & Formulas

## 📚 Essential Equations Cheat Sheet

### 🧬 Growth Models

| Model | Equation | Use Case |
|-------|----------|----------|
| **Exponential** | $\frac{dN}{dt} = rN$ | Unlimited growth |
| **Logistic** | $\frac{dN}{dt} = rN(1-\frac{N}{K})$ | Limited resources |
| **Von Bertalanffy** | $\frac{dL}{dt} = k(L_\infty - L)$ | Individual size |
| **Gompertz** | $\frac{dN}{dt} = -rN\ln(\frac{N}{K})$ | Tumor growth |

### ⚗️ Enzyme Kinetics

| Concept | Formula |
|---------|---------|
| **Michaelis-Menten** | \(v = \frac{V_{max}[S]}{K_m + [S]}\) |
| **Lineweaver-Burk** | \(\frac{1}{v} = \frac{K_m}{V_{max}}\frac{1}{[S]} + \frac{1}{V_{max}}\) |
| **Monod (microbial growth)** | \(\mu = \mu_{max}\frac{S}{K_s + S}\) |

---

### 🧮 Differentiation & Numerical Methods

| Topic | Key Formula / Idea |
|-------|--------------------|
| First derivative | \(\frac{dy}{dx}\): instantaneous rate of change |
| Second derivative | \(\frac{d^2y}{dx^2}\): curvature / acceleration |
| Euler method | \(y_{n+1} = y_n + h f(t_n, y_n)\) |
| RK4 step | \(y_{n+1} = y_n + \frac{h}{6}(k_1 + 2k_2 + 2k_3 + k_4)\) |

---

### 🎯 Population & Epidemiology

| Model | Core Relation |
|-------|---------------|
| Predator-prey | \(\frac{dx}{dt} = \alpha x - \beta xy,\ \frac{dy}{dt} = \delta xy - \gamma y\) |
| Competition | \(\frac{dN_i}{dt} = r_iN_i\left(\frac{K_i - N_i - \sum_{j\neq i}\alpha_{ij}N_j}{K_i}\right)\) |
| SIR | \(\frac{dS}{dt} = -\beta SI,\ \frac{dI}{dt} = \beta SI - \gamma I,\ \frac{dR}{dt} = \gamma I\) |

---

### 🧭 Quick Exam Tips

- Always state **assumptions** clearly before writing the model.  
- Identify **variables, parameters, and units** explicitly.  
- Draw a **small flowchart or block diagram** for interaction models.  
- When stuck: check **dimensions**, **limits** (e.g., \(t \to 0\), \(t \to \infty\)), and **equilibria**.  
- For numerical questions, write at least **one explicit step** of Euler/RK4 or algebra.

---

**✨ End of Mathematical Modeling Notes – Exam-Ready Version ✨**

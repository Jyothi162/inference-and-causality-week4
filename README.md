# Session 7 and 8 — Do-Calculus: Back-Door & Front-Door Criteria

This repository contains the materials for **Week 4** of the *Inference and Causality* course.  
- Slides: see [`slides/`](./slides/) folder  
- Notebooks: see [`notebooks/`](./notebooks/) folder  

---

## 📑 Sessions Outline
### Back-Door Adjustment • Front-Door Adjustment • Confounding and Path Blocking  
### Introduction to Do-Calculus Rules • Formal Identification with DAGs

---

## Learning Objectives
By the end of this week, you will be able to:

- Explain the distinction between **observation** and **intervention** in causal inference.  
- Identify **confounders** and **mediators** in a directed acyclic graph (DAG).  
- Apply the **Back-Door Criterion** to find valid adjustment sets.  
- Understand when **Back-Door adjustment fails** and when **Front-Door adjustment** can identify causal effects.  
- Derive and compute **P(Y | do(X))** using both back-door and front-door formulas.  
- Recognize the connection between these criteria and the **formal rules of Do-Calculus**.  
- Prepare for applying algebraic **Do-Calculus transformations** in Session 8.

---

## Week 4 Structure

| Session | Topic |
|:--------|:------|
| **Session 7** | Back-Door Adjustment • Front-Door Adjustment • Confounding and Path Blocking |
| **Session 8** | The Three Rules of Do-Calculus • Generalizing Back-Door and Front-Door |

---

## Session Notebook Materials

### [1_InferenceAndCausality_Week4_BackDoor.ipynb](notebooks/1_InferenceAndCausality_Week4_BackDoor.ipynb)
Hands-on demonstration of the **Back-Door Criterion**:
- Simulate data with an unobserved common cause.  
- Identify valid adjustment sets Z.  
- Estimate `P(Y | do(X)) = ∑₍z₎ P(Y | X,z) P(z)` using both analytical and empirical methods.  
- Visualize how conditioning on Z removes confounding.  

---

### [2_InferenceAndCausality_Week4_FrontDoor.ipynb](notebooks/2_InferenceAndCausality_Week4_FrontDoor.ipynb)
Implementation of the **Front-Door Criterion**:
- Explore a mediated causal chain (e.g., *Smoking → Tar → Cancer*).  
- Check all three front-door conditions.  
- Compute the causal effect via  
  `P(Y | do(X)) = ∑₍z₎ P(Z | X) ∑₍x'₎ P(Y | X', Z) P(X')`.  
- Compare numerical and simulated results.  

---

## Key Concepts

| Concept | Description |
|:--------|:-------------|
| **Confounder** | A variable that opens a non-causal path between X and Y. |
| **Back-Door Criterion** | Blocks all paths into X that create spurious correlations. |
| **Front-Door Criterion** | Uses a mediator Z to bypass hidden confounding when back-door fails. |
| **Adjustment Formula** | Expresses interventional probability `P(Y|do(X))` as a sum over observed quantities. |
| **Collider Bias** | Conditioning on a common effect can *open* a false path. |
| **Do-Calculus** | Set of three algebraic rules allowing the transformation of expressions containing `do(·)` into observational probabilities. |

---

## Homework
Complete the exercises at the end of each notebook and push your updates to your forked repository.  

---
## 🚀 Environment Setup

Before starting, please **fork this repository** and create a fresh Python virtual environment.  
All required libraries are listed in `requirements.txt`.

> ⚠️ If you encounter errors during `pip install`, try removing the version pinning for the failing package(s) in `requirements.txt`.  
> On Apple M1/M2 systems you may also need to install additional system packages (the “M1 shizzle”).

---

### macOS / Linux (bash/zsh)

```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
source .venv/bin/activate

# Upgrade pip and install dependencies
pip install --upgrade pip
pip install -r requirements.txt
```

### Windows (PowerShell)
```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
.venv\Scripts\Activate.ps1

# Upgrade pip and install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### Windows (Git Bash)
```bash
# Select Python version (if using pyenv)
pyenv local 3.11.3

# Create and activate virtual environment
python -m venv .venv
source .venv/Scripts/activate

# Upgrade pip and install dependencies
python -m pip install --upgrade pip
pip install -r requirements.txt
```

You’re now ready to run the session notebooks!

Deactivate the environment when you’re done:
```bash
deactivate
```

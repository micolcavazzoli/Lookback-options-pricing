# Lookback Option Pricing

## Overview

This project implements a Monte Carlo pricing engine for European floating-strike lookback options under the Black-Scholes framework.

The pricing engine was developed in **C++**, while the user interface was built in **Microsoft Excel using VBA**. The two components communicate through a **Dynamic Link Library (DLL)**, providing an interactive environment for pricing and sensitivity analysis.

---

## Financial Background

A lookback option is a path-dependent derivative whose payoff depends on the maximum or minimum value reached by the underlying asset during the life of the contract.

### Floating-Strike Lookback Call

```math
\text{Payoff} = S(T)-\min_{0\leq t\leq T}S(t)
```

### Floating-Strike Lookback Put

```math
\text{Payoff} = \max_{0\leq t\leq T}S(t)-S(T)
```

---

## Project Objectives

The project focuses on:

- Pricing European lookback options using Monte Carlo simulation
- Implementing the numerical engine in C++
- Building an Excel-based user interface with VBA
- Computing the main option Greeks
- Producing graphical analysis of price and Delta behaviour

---

## Features

### Pricing Engine

- Monte Carlo simulation under the Black-Scholes model
- Simulation of geometric Brownian motion paths
- Support for floating-strike lookback calls and puts
- Discounted expected payoff estimation

### Risk Sensitivities

The application computes:

- Price
- Delta
- Gamma
- Theta
- Vega
- Rho

### Visualization

The Excel interface allows the visualization of:

- Option price as a function of the underlying asset price
- Delta as a function of the underlying asset price

---

## Technology Stack

| Component | Technology |
|---|---|
| Pricing Engine | C++ |
| User Interface | Excel VBA |
| Integration | DLL |
| Numerical Method | Monte Carlo Simulation |
| Financial Model | Black-Scholes |

---

## Inputs

The application accepts the following inputs:

| Parameter | Description |
|---|---|
| Valuation Date | Pricing date |
| Maturity | Option maturity |
| Option Type | Call / Put |
| Spot Price | Current underlying price |
| Risk-Free Rate | Constant interest rate |
| Volatility | Black-Scholes volatility |
| Monte Carlo Parameters | Number of simulations and discretization settings |

---

## Project Structure

```text
Lookback-options-pricing/
│
├── C++ Engine/
│   ├── Monte Carlo simulation
│   ├── Lookback payoff implementation
│   ├── Greeks computation
│   └── DLL export functions
│
├── Excel VBA Interface/
│   ├── User input interface
│   ├── VBA functions
│   ├── DLL calls
│   └── Charts generation
│
├── Project Assignment/
│   └── Project specification PDF
│
└── README.md
```

---

## Methodology

The underlying asset price is modeled using the Black-Scholes dynamics:

```math
dS_t = rS_tdt + \sigma S_tdW_t
```

where:

- \(S_t\) is the underlying asset price
- \(r\) is the constant risk-free rate
- \(\sigma\) is the volatility
- \(W_t\) is a Brownian motion

The Monte Carlo algorithm follows these steps:

1. Simulate a large number of asset price paths
2. Record the running minimum or maximum of each path
3. Compute the lookback payoff for each simulated path
4. Discount the average payoff to present value
5. Estimate Greeks using finite-difference approximations

---

## Example Workflow

1. Enter the market parameters in Excel
2. Select the option type: Call or Put
3. Choose the Monte Carlo simulation settings
4. Run the pricing engine
5. Retrieve:
   - Option price
   - Greeks
   - Price chart
   - Delta chart

---

## Key Skills Demonstrated

- Quantitative Finance
- Derivatives Pricing
- Monte Carlo Methods
- Black-Scholes Modeling
- C++
- VBA Development
- Excel Integration
- Numerical Methods
- Financial Engineering

---

## References

- John Hull, *Options, Futures and Other Derivatives*
- Paul Wilmott, *Mathematics of Financial Derivatives*
- Paul Glasserman, *Monte Carlo Methods in Financial Engineering*
- Gilles Pagès, *Numerical Probability*
- Emmanuel Gobet, *Monte-Carlo Methods and Stochastic Processes*

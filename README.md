# Least Squares Monte Carlo (LSMC) for Pricing American Put Options

This project implements the Least Squares Monte Carlo (LSMC) method to price American put options. The LSMC method is a popular approach for pricing American options, where early exercise is possible. In this implementation, we use Chebyshev polynomials as basis functions to approximate the continuation value of the option, and Monte Carlo simulations to estimate the expected option payoff.

## Overview

The problem is solved using the following steps:

1. **Simulate Stock Price Paths**: We simulate the evolution of the stock price using a geometric Brownian motion model.
2. **Compute Payoff**: For each simulated path, we compute the payoff of the American put option at each time step.
3. **Apply Least Squares Monte Carlo (LSMC)**: We use polynomial basis functions (Chebyshev polynomials) to approximate the continuation value at each time step.
4. **Backward Induction**: Starting from the last time step, we perform backward induction to determine whether to exercise or continue holding the option at each time step, using the LSMC method.

## Problem Setup

### Parameters:
- **σ (volatility)** = 0.04
- **r (interest rate)** = 0.01
- **K (strike price)** = 35
- **T (maturity time)** = 1 year
- **Δt (time step)** = 0.01
- **Spot (initial stock price)** = 36
- **Order (degree of Chebyshev polynomials)** = 12
- **n (number of simulations)** = 100,000
- **m (number of time steps)** = 50

### Option Type:
- **American Put Option**: An option that allows the holder to exercise it at any time before or at maturity.

### Design Choices:
- **Chebyshev Basis**: Used to represent the continuation value function as a polynomial expansion.
- **Monte Carlo Simulation**: Used to simulate multiple stock price paths for pricing the option.
- **Backward Induction**: Used to determine the optimal exercise strategy at each time step.


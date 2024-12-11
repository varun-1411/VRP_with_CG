# :truck: Capacitated Vehicle Routing Problem (VRP) with Price-and-Branch Approach

## Overview

This project solves **variants of the Capacitated Vehicle Routing Problem (CVRP)** using the **Price-and-Branch (PnB)** method. The focus is on a realistic two-demand scenario, where customer demand is split into two types:

1. **Type I**: Represented by odd-numbered customers (e.g., dry waste, cow milk).
2. **Type II**: Represented by even-numbered customers (e.g., wet waste, buffalo milk).

The models are designed to minimize routing costs under two specific scenarios:

- **Scenario A**: Mixing of demand types is **not allowed**. Each vehicle serves only one demand type.
- **Scenario B**: Mixing is **allowed** but with **segregated capacities** (imagine trucks with two compartments).

---

## Objective

1. Solve CVRP using the **Price-and-Branch** approach.
2. Implement **column generation** for solving the pricing sub-problems using the [cspy library](https://cspy.readthedocs.io/en/latest/).
3. Develop solutions for two realistic scenarios involving demand segregation.
4. Measure and report performance metrics like LP relaxation, solution GAP, and computational time.

---

## Data 

The project uses benchmark VRP instances provided in the **Uchoa-VRP-Set-X** folder. These instances are derived from the well-known **VRP library**:

- [VRP Instances Description](http://vrp.galgos.inf.puc-rio.br/index.php/en/)

The input data includes details such as:
- Customer locations
- Demands (Type I and Type II)
- Vehicle capacities
- Distance matrices

---

## Problem Scenarios

### Scenario A: No Mixing Allowed
- Vehicles serve **only one type** of demand (either Type I or Type II).
- Routing must ensure vehicles remain exclusive to one demand type.

### Scenario B: Mixing Allowed with Segregated Capacities
- Vehicles are equipped with **two compartments** for Type I and Type II demands.
- Two types of vehicles are used:
  1. Vehicles with capacities \((\max_{i \text{ is odd}} d_i, C - \max_{i \text{ is odd}} d_i)\)
  2. Vehicles with capacities \((\max_{i \text{ is even}} d_i, C - \max_{i \text{ is even}} d_i)\)

---

## Methods and Approach

### Price-and-Branch (PnB)
1. **Root Node LP Relaxation**:
   - Solve the LP relaxation of the CVRP using column generation.
   - Pricing sub-problems identify feasible routes (columns) using the **cspy library**.

2. **Branching**:
   - If the LP relaxation is not optimal within the time limit, branch to solve the integer programming (IP) model.

3. **Scenarios**:
   - Scenario-specific constraints are implemented to handle demand mixing and vehicle capacity segregation.

---

## Features

- **Two-Demand Types**: Separation of Type I and Type II customers.
- **Column Generation**: Solve pricing sub-problems efficiently with the **cspy** library.
- **Two Scenarios**: No mixing and capacity-segregated mixing.
- **Performance Reporting**: Track LP bounds, solution gaps, and runtime.

---

## Setup

### Prerequisites

- Python 3.8+
- Required Libraries:
  - `cspy` for column generation
  - `gurobipy` (or another LP/IP solver)
  - `numpy` and `pandas` for data processing

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/your_username/vrp-price-and-branch.git
   cd vrp-price-and-branch


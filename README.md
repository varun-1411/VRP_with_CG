[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/3B_bbQmg)
# :memo: Assignment 4

## Objective

In this assignment, you are required to solve variants of the capacitated VRP using a price and branch approach (PnB). The pricing sub-problems can be solved using [[cspy]](https://cspy.readthedocs.io/en/latest/) library. 

In this variant the demand is assumed to be of two types. Odd numbered customers represent demand of Type I and even numbered customers represent demand of Type II. For example, the problem could be a waste collection model where the two types refer to dry and wet waste or it could be a milk collection example where the customers are farms and the types represent cow and buffalo milk. You are to find minimum cost routing solution (any number of vehicles can be used) under the following scenarios:

Scenario A: Mixing of demand types is not allowed. That is a vehicle can only serve Type I customers or Type II customers but not both.
Scenario B: Mixing is allowed but the capacity (C) is seggregated (imagine two compartments in a truck) and you have two types of vehicle fleet with capacities $(\max_{i \text{ is odd}} d_i, C - \max_{i \text{ is odd}} d_i)$ and $(\max_{i \text{ is even}} d_i, C - \max_{i \text{ is even}} d_i)$

## Data 
The data on which your models must be run is in folder Uchoa-Vrp-Set-X which is a subset of data from the following source. 
- VRP Instances [[Description]](http://vrp.galgos.inf.puc-rio.br/index.php/en/)

## Problems
- Set a time limit of 300 s and report the following information by uploading a PDF response file in your repository. 

| Scenario  | Instance | Root Node LP | Best PnB IP Solution | GAP | Time for Column Generation | Time for IP 
| ----------| -------- |------------- | -------------------- | --- | ---------------------------| ----------- |
| A  |   |   |   |    |   |  |
| B  |   |   |   |    |   |  |

## Rules and Dos and Don'ts
- The total time limit is 300 s. If the root node LP is not solved optimally, you may choose to switch to branching and solve the IP. 
- The time for your codes must include data processing and solving the LP and IP models. 

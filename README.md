# DSC211 – Assignment  
**Student Name:** Jessica Rehal  
**Student ID:** IMS24110  
**Course:** DSC211  
**Topic:** Graph Partitioning using Spectral Methods  
**Dataset:** Zachary’s Karate Club Network  

---

# Modularity on the Karate Club Graph (DSC212)

This repository contains a Python project for the "DSC212: Graph Theory Module" assignment. The project implements a spectral modularity method from scratch to perform community detection on Zachary's Karate Club network.

The core of the project is in the `DSC 211.ipynb` Jupyter Notebook, which details the implementation, analysis, and visualization.

## Project Overview

The goal of this assignment is to implement a recursive community detection algorithm based on modularity maximization. The algorithm uses spectral graph theory to repeatedly bipartition the graph (or its subgraphs) into two communities. This split is determined by the leading eigenvector of the modularity matrix ($B$) for the given community.

The process stops when a community cannot be split further in a way that increases the graph's overall modularity (indicated by a non-positive leading eigenvalue).

## Implementation Details

The notebook `DSC 211.ipynb` is structured as follows:

1.  **Graph and Modularity Matrix Initialization**:

      * Zachary's Karate Club graph is loaded using `networkx`.
      * The Modularity Matrix ($B$) is calculated using the formula:
        $B = A - \frac{kk^T}{2m}$
        (where $A$ is the adjacency matrix, $k$ is the degree vector, and $m$ is the total number of edges).

2.  **Core Bipartition Function (`spectral_bipartition`)**:

      * For any given graph or subgraph, this function computes its modularity submatrix ($B_{sub}$).
      * It then finds the leading eigenvalue ($\lambda_1$) and corresponding eigenvector ($u_1$) of $B_{sub}$ using `scipy.linalg.eigh`.
      * **Stopping Condition**: If $\lambda_1 \le 0$, the community is considered indivisible, and the function stops.
      * **Splitting**: If $\lambda_1 > 0$, the community is split into two new communities based on the sign of the elements in the eigenvector $u_1$.

3.  **Recursive Community Detection (`multi_community`)**:

      * This function recursively applies the `spectral_bipartition` function to the graph.
      * It starts with the entire graph, splits it, and then recursively attempts to split the two resulting sub-communities.
      * It records the history of all splits and the evolution of network metrics at each step.

4.  **Metric Calculation**:

      * A helper function (`metric_calculations`) uses `networkx` to compute the following metrics for nodes within their subgraphs:
          * Degree Centrality
          * Betweenness Centrality
          * Closeness Centrality
          * Clustering Coefficient

5.  **Visualization**:

      * The notebook includes several `matplotlib` visualizations:
          * The initial Karate Club graph.
          * The recursive splitting process, showing how communities are divided at each step.
          * The final community structure identified by the algorithm.
          * The evolution of node metrics (e.g., centrality) as the partitions become more refined.

## Results

The spectral modularity method successfully uncovers the latent factional structure within the Karate Club network. The final visualizations show the graph partitioned into several small, cohesive communities, which align with the known historical split of the club. The analysis of metric evolution (e.g., betweenness centrality) reveals how certain "bridge" nodes are central in the initial graph but become peripheral as their communities are isolated.

## How to Run

1.  Clone this repository.
2.  Ensure you have the required Python libraries installed:
    ```bash
    pip install jupyter networkx numpy scipy matplotlib
    ```
3.  Launch the Jupyter Notebook:
    ```bash
    jupyter notebook "DSC 211.ipynb"
    ```
4.  Run the cells in the notebook from top to bottom to reproduce the analysis and visualizations.

## Dependencies

  * `networkx`
  * `numpy`
  * `scipy`
  * `matplotlib`

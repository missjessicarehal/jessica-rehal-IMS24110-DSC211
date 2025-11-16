# jessica-rehal-IMS24110-DSC211
This project uses recursive spectral modularity to split the Karate Club graph into meaningful communities. By analyzing eigenvectors, modularity gains, and centrality metrics, it reveals how tightly connected groups form and highlights influential nodes in the network.”
# DSC 211 – Graph Partitioning Assignment

This repository contains my solution for the **DSC 211** assignment, implemented in a Jupyter Notebook (`dsc211.ipynb`).  
The assignment focuses on **graph analysis**, **spectral methods**, and **community detection** using the classic *Zachary’s Karate Club* dataset.

---

##  **Overview**
The notebook performs the following tasks:

1. **Load and visualize the Karate Club graph** using NetworkX.  
2. **Compute graph Laplacian matrices** and perform **Spectral Clustering**.  
3. **Calculate eigenvalues and eigenvectors** relevant to graph partitioning.  
4. **Generate a 2-way partition** of the graph based on the Fiedler vector.  
5. **Visualize the predicted partition vs. the true club split**.  
6. **Evaluate partition quality** using cut size and other metrics.

---

##  **Technologies Used**
- Python 3  
- Jupyter Notebook  
- `networkx`  
- `numpy`  
- `pandas`  
- `matplotlib`
- pip install networkx numpy pandas matplotlib
jupyter notebook dsc211.ipynb
   dsc211-assignment
 ┣ 📄 dsc211.ipynb     # Main notebook with all code
 ┣ 📄 README.md        # Project description


---

## 📊 **How to Run**
1. Clone the repository:

```bash
git clone <your-repo-link>

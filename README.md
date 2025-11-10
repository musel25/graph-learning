# Graph Learning: Analysis of Amazon Product Co-purchasing Network

This project performs a detailed graph analysis of the Amazon product co-purchasing network dataset from March 2, 2003. The analysis is conducted in a Jupyter Notebook (`main.ipynb`) and includes the calculation of various graph metrics to understand the structure and properties of the network.

## Dataset

The dataset used is `Amazon0302.txt`, which contains product co-purchasing information from Amazon. It is represented as a directed graph where nodes are products and a directed edge from product `u` to product `v` means that `v` was frequently co-purchased with `u`.

- **Nodes**: Products
- **Edges**: Co-purchasing relationships

The dataset is from the Stanford Network Analysis Project (SNAP) and can be found [here](https://snap.stanford.edu/data/amazon0302.html).

## Analysis

The `main.ipynb` notebook performs the following analysis:

1.  **Data Loading**: Loads the edge list from `Amazon0302.txt`.
2.  **Graph Representation**: Builds a sparse matrix representation of the directed graph and an undirected version for certain metrics.
3.  **Basic Metrics**:
    - Number of nodes and edges.
    - In-degree, out-degree, and undirected degree distributions.
    - Graph density.
4.  **Advanced Metrics**:
    - **Transitivity**: Measures the probability that adjacent nodes of a node are connected (also known as the global clustering coefficient).
    - **Closeness Centrality**: Measures how close a node is to all other nodes in the graph. Due to computational cost, this is calculated for a subset of top-degree nodes.
    - **Betweenness Centrality**: Measures the number of times a node acts as a bridge along the shortest path between two other nodes. This is approximated using a sample of nodes.
5.  **Visualization**: Plots the in-degree, out-degree, and undirected degree distributions on both linear and log-log scales to visualize the power-law nature of the network.
6.  **Results**: The calculated metrics (degrees, transitivity, etc.) are saved to `amazon_metrics.npz` for later use.

## Requirements

The project requires the following Python libraries:

- `numpy`
- `scipy`
- `networkx`
- `matplotlib`
- `jupyter`

You can install them using pip:
```bash
pip install numpy scipy networkx matplotlib jupyter
```

## How to Run

1.  **Clone the repository**:
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```
2.  **Download the dataset**:
    If `Amazon0302.txt` is not already present, download it from the [SNAP website](https://snap.stanford.edu/data/amazon0302.html) and place it in the root directory.
3.  **Run the Jupyter Notebook**:
    ```bash
    jupyter notebook main.ipynb
    ```
    This will open the notebook in your web browser. You can then run the cells to perform the analysis.

## Results

The analysis reveals several key characteristics of the Amazon co-purchasing network:

- It is a large, sparse, and directed graph.
- The degree distributions follow a power-law, which is typical for real-world networks, indicating the presence of hubs (highly connected products).
- The notebook calculates and prints various metrics, providing insights into the network's structure. The final computed metrics are stored in `amazon_metrics.npz`.

# Social Network Analysis with Facebook Dataset

## Overview
This project analyzes the **SNAP Social Circles: Facebook Dataset** using Python, focusing on network analysis and visualization techniques. The dataset represents a social network as an undirected graph, where nodes are users and edges represent friendships. The project explores the graph's properties, visualizes the network, and applies community detection using spectral clustering, evaluating the results with various metrics.

## Project Structure
- **File**: `Data_Visualisation_UL_Project_F.ipynb`
  - A Jupyter Notebook containing the code for loading the dataset, analyzing the graph, visualizing it, and computing community detection metrics.
- **Dataset**: `facebook_combined.txt`
  - A text file containing edges of the Facebook social network, where each line represents a friendship between two nodes (users).

## Requirements
To run the project, ensure you have the following Python libraries installed:
```bash
pip install networkx matplotlib numpy scikit-learn
```

## Key Components
1. **Required Libraries**:
   - `networkx`: For graph creation and analysis.
   - `matplotlib`: For visualizing the graph.
   - `numpy`: For numerical computations.
   - `scikit-learn`: For clustering and evaluation metrics (e.g., KMeans, silhouette score, Calinski-Harabasz score).

2. **Dataset Loading**:
   - The `read_facebook_dataset` function reads the `facebook_combined.txt` file and constructs an undirected graph using `networkx.Graph`.
   - The dataset is assumed to be stored at `/content/drive/MyDrive/UL/Project Dataset/facebook_combined.txt`.

3. **Graph Analysis**:
   - Computes basic graph properties:
     - Number of nodes and edges.
     - Maximum and minimum node degrees.
     - Average degree and graph density.
     - Connectivity and diameter.
     - Top 5 nodes by highest and lowest degrees.
     - Number of connected components and size of the largest component.
     - Average clustering coefficient and average shortest path length.

4. **Graph Visualization**:
   - Uses `networkx.spring_layout` for node positioning.
   - Visualizes the graph with `matplotlib`, displaying nodes as blue dots with a small size for clarity.

5. **Community Detection**:
   - Applies spectral clustering to identify communities within the graph.
   - Evaluates clustering quality using:
     - **Modularity**: Measures the strength of community structure.
     - **Normalized Cut Ratio**: Assesses the quality of partitions.
     - **Silhouette Score**: Evaluates how well-separated clusters are.
     - **Total Compactness**: Measures intra-cluster cohesion.
     - **Calinski-Harabasz Score**: Assesses cluster separation and cohesion.
     - **Separability**: Quantifies inter-cluster separation.

## How to Run
1. **Set Up Environment**:
   - Install the required libraries using the command above.
   - Ensure the dataset file (`facebook_combined.txt`) is accessible at the specified path or update the path in the notebook.

2. **Run the Notebook**:
   - Open `Data_Visualisation_UL_Project_F.ipynb` in Jupyter Notebook or JupyterLab.
   - Execute the cells sequentially to:
     - Load and process the dataset.
     - Analyze the graph properties.
     - Visualize the network.
     - Perform spectral clustering and compute evaluation metrics.

3. **Expected Outputs**:
   - Printed graph statistics (e.g., number of nodes, edges, degree metrics, etc.).
   - A visual plot of the graph using the spring layout.
   - Clustering metrics (modularity, silhouette score, etc.) printed to the console.

## Notes
- The notebook assumes the dataset is stored in a Google Drive path (`/content/drive/MyDrive/UL/Project Dataset/facebook_combined.txt`). Adjust the path if running locally or on a different platform.
- The spectral clustering section references `spectral_communities`, which is not defined in the provided code snippet. Ensure this variable is computed earlier in the notebook (likely using `SpectralClustering` from `scikit-learn`).
- The `total_compactness` and `calculate_separability` functions are not shown in the provided code. Verify that these are defined in the notebook or implement them as needed.

## Dataset
The dataset is sourced from the SNAP (Stanford Network Analysis Project) repository and represents a Facebook social network with 4,039 nodes and 88,234 edges. Each line in `facebook_combined.txt` contains two node IDs, indicating a friendship.

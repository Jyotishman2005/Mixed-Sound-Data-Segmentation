# K-means Clustering for Mixed Sound Data Analysis
Designed and implemented a K-means clustering model to segment mixed sound data




## Project Overview
This project focuses on applying K-means clustering, an unsupervised machine learning technique, to segment mixed sound data. The goal is to identify inherent groupings within the dataset based on various features such as Gender, Heart Sound Type, Lung Sound Type, and Location. This analysis can help in understanding the natural structure of the data and potentially in developing diagnostic or classification systems for sound analysis.

## Dataset
The analysis utilizes three primary CSV files:
- `Mix.csv`: Contains mixed sound data with attributes like Gender, Heart Sound Type, Lung Sound Type, Location, and corresponding IDs.
- `HS.csv`: Contains heart sound specific data.
- `LS.csv`: Contains lung sound specific data.

(Note: The specific contents and size of these datasets are detailed in the notebook's initial data loading and inspection steps.)

## Methodology
1.  **Data Loading & Initial Inspection**: Loaded `Mix.csv`, `HS.csv`, and `LS.csv` into pandas DataFrames and performed basic checks for missing values and data types.
2.  **Data Preprocessing**: 
    - Categorical features (`Gender`, `Heart Sound Type`, `Lung Sound Type`, `Location`) from `Mix.csv` were transformed using **one-hot encoding**.
    - ID columns (`Heart Sound ID`, `Lung Sound ID`, `Mixed Sound ID`) were dropped to prevent their interference with clustering.
    - The preprocessed data was then scaled using `StandardScaler` to ensure all features contribute equally to the distance calculations in K-means.
3.  **Optimal K Determination**: The **Elbow Method** was used to determine the optimal number of clusters (`K`). A plot of inertia versus the number of clusters was generated to identify the 'elbow point'.
4.  **K-means Clustering**: K-means clustering was performed with `K=3` and `K=2` (based on observations from the Elbow Method) on the scaled data.
5.  **Dimensionality Reduction & Visualization**: **Principal Component Analysis (PCA)** was applied to reduce the high-dimensional data to two principal components, allowing for 2D visualization of the clusters.
6.  **Results Export and Comparison**: Cluster assignments for both `K=2` and `K=3` were merged with the original `Mixed Sound ID` and exported to `clusters_k2.csv` and `clusters_k3.csv`. A cross-tabulation was performed to compare the similarity of cluster assignments between the two K values.

## Results and Visualizations
- The Elbow Method plot indicates potential optimal `K` values (e.g., 2 or 3 clusters).
- PCA visualizations for both `K=2` and `K=3` show distinct cluster formations.
- Cross-tabulation provides a quantitative comparison of how data points are grouped differently when using 2 versus 3 clusters.

*(You can include screenshots of the Elbow Method plot and the PCA scatter plots here for better illustration if you convert them to images.)*

## Files
- `KMeans_Project.ipynb`: The main Jupyter/Colab notebook containing all the analysis steps.
- `Mix.csv`: The primary dataset for mixed sound data.
- `HS.csv`: Dataset for heart sounds.
- `LS.csv`: Dataset for lung sounds.
- `clusters_k2.csv`: CSV file containing 'Mixed Sound ID' and assigned clusters for `K=2`.
- `clusters_k3.csv`: CSV file containing 'Mixed Sound ID' and assigned clusters for `K=3`.

## Installation & Usage
To run this notebook locally, you'll need Python and the following libraries:

```bash
pip install pandas scikit-learn matplotlib seaborn



Clone this repository:
git clone https://github.com/YourUsername/YourRepoName.git
cd YourRepoName
Open the k_means_clustering_mixed_sound_data.ipynb file in a Jupyter environment (e.g., Jupyter Lab, Google Colab).
Run all cells in the notebook to reproduce the analysis and results.

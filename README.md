PCA on Financial Returns

Objective
Apply Principal Component Analysis (PCA) to the correlation matrix of daily stock returns to identify the main risk factors (“market” and “sector” components) and demonstrate dimensionality reduction in financial data.

Overview
Concept: PCA decomposes the correlation matrix of asset returns into orthogonal components (eigenvectors). The first few components explain most of the variance, typically one large “market factor” and smaller sector or style factors.

Data: Daily adjusted closing prices for 15 large-cap U.S. stocks (AAPL, MSFT, NVDA, GOOGL, AMZN, META, JPM, BAC, XOM, CVX, JNJ, PG, PEP, KO, COST) downloaded via yfinance for 2023–2025.

Steps:

1. Compute daily log returns
2. Build the correlation matrix
3. Perform PCA using sklearn.decomposition.PCA
4. Visualize explained variance and factor loadings
5. (Optional) Reconstruct correlation matrix from top components
6. (Optional) Compute factor returns

Outputs
Eigenvalue Spectrum – variance explained by each principal component
Cumulative Variance Plot – fraction of total variance captured by top components
First Eigenvector Loadings – portfolio weights of the “market factor”
(Optional) correlation reconstruction and factor return series

Interpretation
PC1 (first component): represents overall market co-movement
PC2–PCk: represent sector or style-specific deviations
Cumulative variance: typically 80–90% of total variance captured by the first 3–4 components

Usage
Clone the repository, install the requirements, and run the notebook in Jupyter.

git clone [https://github.com/](https://github.com/)<your-username>/pca_finance.git
cd pca_finance
python -m venv .venv
.venv\Scripts\activate  (Windows)
source .venv/bin/activate  (macOS/Linux)
pip install -r requirements.txt
jupyter notebook pca_finance.ipynb

Run all cells in the notebook. Plots will appear inline.

Mathematical Background
Given the correlation matrix Σ:
Σ v_i = λ_i v_i
λ_i is the variance explained by component i, and v_i is the orthogonal factor direction.
Low-rank reconstruction: Σ^(k) = Σ_{i=1}^k λ_i v_i v_i^T.
This shows how most of the explanatory structure can be retained using only a few principal components.

Resume Summary
Applied Principal Component Analysis to stock return correlations, identified dominant risk factors, and reconstructed correlations using top eigenvectors to demonstrate dimensionality reduction.

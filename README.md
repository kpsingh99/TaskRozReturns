<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
</head>
<body>
  <h1>🧠 Regime Detection via Unsupervised Learning</h1>

  <p>This project focuses on <strong>market regime segmentation</strong> using unsupervised learning techniques applied to <strong>order book depth data</strong> and <strong>trade volume data</strong>. The aim is to cluster market behavior into distinct regimes like <em>Trending</em>, <em>Mean-Reverting</em>, <em>Volatile</em>, <em>Stable</em>, <em>Liquid</em>, and <em>Illiquid</em> states without labeled data.</p>

  <h2>📌 Objective</h2>
  <p>To identify and analyze different market regimes using clustering based on:</p>
  <ul>
    <li><strong>Trending vs Mean-Reverting</strong></li>
    <li><strong>Volatile vs Stable</strong></li>
    <li><strong>Liquid vs Illiquid</strong></li>
  </ul>

  <h2>📂 Data</h2>
  <ul>
    <li><code>depth20</code>: Top 20 levels of order book data (bid/ask prices and quantities)</li>
    <li><code>aggTrade</code>: Trade volume data (event or time-based)</li>
  </ul>
  <p>Access the dataset via this 
    <a href="https://drive.google.com/drive/folders/1gFLwPLTE0nUN-MHoOn5u_1yrlbpI3Fst?usp=sharing" target="_blank">Google Drive Link</a>
  </p>

  <h2>🛠️ Steps Followed</h2>

  <h3>1. Feature Engineering</h3>
  <ul>
    <li><strong>Order Book Features</strong>: Bid-ask spread, Imbalance, Microprice, Cumulative depth, Sloped depth</li>
    <li><strong>Price Action & Volatility</strong>: Rolling log returns, Short-term volatility (10s, 30s)</li>
    <li><strong>Volume-Based Features</strong>: Volume imbalance, Cumulative volume, VWAP shift</li>
    <li><strong>Derived Features</strong>: Trade wipe level, Depth decay rates</li>
  </ul>

  <h3>2. Data Normalization</h3>
  <p>Applied standard normalization techniques (Z-score / Min-Max). Optionally performed dimensionality reduction using <strong>PCA</strong>.</p>

  <h3>3. Clustering</h3>
  <p>Explored multiple clustering algorithms:</p>
  <ul>
    <li>K-Means (used elbow method to choose k)</li>
    <li>HDBSCAN (for noise-handling and non-spherical clusters)</li>
    <li>Gaussian Mixture Models (for soft clustering)</li>
  </ul>
  <p>Evaluated clustering quality using:</p>
  <ul>
    <li>Silhouette Score</li>
    <li>Davies-Bouldin Index</li>
  </ul>

  <h3>4. Regime Labeling</h3>
  <p>Each timestamp was labeled with a regime type. Each regime cluster was analyzed for:</p>
  <ul>
    <li>Average volatility</li>
    <li>Typical spread and liquidity</li>
    <li>Price behavior (trendiness)</li>
  </ul>

  <h3>5. Visualization</h3>
  <ul>
    <li>Regime vs Time plots</li>
    <li>Overlay on price chart</li>
    <li>Dimensionality reduction (t-SNE, UMAP) for cluster visualization</li>
  </ul>

  <h3>6. Regime Transitions</h3>
  <p>Analyzed <strong>transition probabilities</strong> between regimes. Example:</p>
  <blockquote>What is the chance that a "Mean-Reverting & Illiquid" state turns into a "Trending & Liquid" state?</blockquote>

  <h2>📊 Deliverables</h2>
  <ul>
    <li><code>market_study.ipynb</code>: Jupyter Notebook with code and outputs</li>
    <li>Report (PDF): Summary of methods, visualizations, and insights</li>
  </ul>

</body>
</html>

# Wholesale Customer Segmentation Using PCA and Clustering

A Python-based analysis of **wholesale customer purchasing patterns** using **Principal Component Analysis (PCA)**, **K-means**, and **hierarchical clustering**. The project compares the clustering results and interpretations with an analysis produced using **Google Gemini**.

## Project overview

The project examines differences in wholesale customers' annual spending and evaluates how clustering methods group customers with similar purchasing patterns. It combines exploratory data analysis, dimensionality reduction, clustering, and a comparison with LLM-generated analysis.

The analysis covers:

- **Exploratory Data Analysis:** Examine spending distributions, outliers, correlations, and customer characteristics.
- **Principal Component Analysis:** Reduce the spending variables to a smaller set of components and interpret the main patterns in purchasing behaviour.
- **Customer Clustering:** Compare K-means and hierarchical clustering using Ward and complete linkage.
- **LLM Comparison:** Compare the analytical choices and interpretations with results generated using Google Gemini.

## Dataset

The wholesale customer dataset contains **440 observations**, with six numerical variables describing annual spending on **Fresh, Milk, Grocery, Frozen, Detergents/Paper, and Delicatessen** products.

Two categorical variables describe customers' **Channel** (HoReCa or Retail) and **Region** (Lisbon, Oporto, or Other). The six spending variables are used for PCA and clustering, while channel and region provide context for interpreting customer groups.

**Data source:** [Wholesale Customers — UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/292/wholesale+customers)  
**Dataset citation:** Cardoso, M. (2013). *Wholesale Customers* [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5030X  
**Licence:** Creative Commons Attribution 4.0 International (CC BY 4.0).

The original dataset is stored in the `data/` directory as `Wholesale customers data.csv`.

## Methodology

The project follows an unsupervised machine learning workflow to identify patterns in customer purchasing behaviour. Spending data are explored and standardised before PCA is used to reduce dimensionality. K-means and hierarchical clustering are then applied to the transformed data, and the resulting customer groups are compared using clustering quality measures and interpretability.

A separate LLM-based analysis is examined to compare methodological choices, cluster selection, and the interpretation of customer segments.

## Results

PCA retains **three principal components**, explaining **84.79%** of the variation in the six spending variables. The clustering methods produce different customer groupings:

| Method | Selected clusters | Reported findings |
|---|---:|---|
| K-means | 2 | Silhouette score of 0.64; a broad separation in spending patterns |
| Hierarchical clustering (Ward) | 3 | More detailed segments with different purchasing profiles |
| Hierarchical clustering (complete linkage) | 4 | Highly uneven cluster sizes, including a single-customer cluster |

The report finds that K-means offers a simpler two-group segmentation, while Ward hierarchical clustering provides more detailed customer profiles. The Gemini comparison shows differences in component selection, cluster selection, and the level of explanation provided without further prompting.

## Technology stack

- **Python** — data analysis and modelling
- **pandas and NumPy** — data preparation and numerical analysis
- **scikit-learn** — PCA, K-means, clustering evaluation, and preprocessing
- **SciPy** — hierarchical clustering and dendrograms
- **Matplotlib and Seaborn** — exploratory and clustering visualisations
- **Google Gemini** — LLM-based comparative analysis

## Project files

```text
.
├── data/
│   └── Wholesale customers data.csv  # Original UCI dataset
├── Group3_SMM636.ipynb   # PCA, clustering, and analysis notebook
├── Report.pdf            # Accompanying report and discussion
└── README.md             # Project documentation
```

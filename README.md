# Taiwan Credit Card Default Risk Analytics (R)

An exploratory data analysis (EDA) and advanced visualization project in R investigating customer default payments in Taiwan. Using a dataset of 30,000 credit clients, this project isolates key financial drivers across different credit limit tiers and leverages interactive visualization techniques to uncover indicators of financial distress and default risk.

🔗 **[Live Project Interactive Dashboard](https://github.io)**

---

## 📌 Project Overview
* **Goal**: Analyze 23 independent variables (demographics, credit history, bill scales, and payment amounts) to determine key indicators of credit default risk.
* **Key Findings**: 
  * Isolated `Max Bill Amount` and `Mean Pay Amount` as the primary financial drivers across all credit limit tiers.
  * Individuals with a higher `Max Bill Amount` and `Mean Pay Amount` are likely to have a higher Credit Limit Tier. 
  * Individuals classified as High or Very High Credit Limit Tier and Non-Defaulters have significantly higher `Mean Pay Amount` and `Max Bill Amount` compared to Defaulters. 
  * Those with a lower `Mean Pay Amount` are consistently more likely to be Defaulters.
* **Methodology**: Multi-stage data exploration utilizing Principal Component Analysis (PCA) for feature screening, scatter/sine plots for initial trends, and LOESS-smoothed curves to capture the relationship between `Mean Pay Amount` and `Max Bill Amount`.

---

## 💾 Dataset Information
This project utilizes the classic **Default of Credit Card Clients Dataset** sourced from the UCI Machine Learning Repository.

* **Source URL**: [UCI Machine Learning Repository - Dataset 350](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)
* **Original Publication**: Yeh, I., & Lien, C. (2009). The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients. *Expert Systems with Applications*, 36, 2473-2480. [DOI Link](https://doi.org/10.1016/J.ESWA.2007.12.020)
* **Volume**: 30,000 instances, including 23 independent variables and one binary response variable indicating default payment status (1 for default, 0 for no default), 0 missing values.

---

## 📄 License
The CC BY 4.0 license allows anyone to copy, redistribute the material for any purpose, even commercially, and remix, transform, and build upon the material for any purpose, but we must give appropriate credit.Users cannot impose restrictions that limit others’ rights under this license.

---

### Repository Structure
* **`R_project.Rmd`**: Main R Markdown workbook housing data preprocessing, PCA calculations, analytics pipelines, and Plotly dashboard configurations.
* **`index.html`**: Compiled interactive web output mapped for automatic hosting via GitHub Pages.
* **`gg_a.png` & `gg_b.png`**
  * **Figure 1**: Scatter plots and density plots for Non-Defaulters to identify potentially interesting patterns.
  * **Figure 2**: Scatter plots and density plots for Defaulters to identify potentially interesting patterns.
* **`combined_plot_a.png` & `combined_plot_b.png`**
  * **Figure 3**: Box Plot + Jitter Plot for Non-Defaulters to visualize the relationship between the Credit Limit Tier and continuous factors.
  * **Figure 4**: Box Plot + Jitter Plot for Defaulters to visualize the relationship between the Credit Limit Tier and continuous factors.
* **`combined_pca.png`**
  * **Figure 5**: PCA plot for continuous features and the Credit Limit Tier of Non-Defaulters and Defaulters.
* **`pca_plot_all.png`**
  * **Figure 6**: PCA plot for continuous features and the Credit Limit Tier of Non-Defaulters and Defaulters combined in a single figure.
* **`scatter_plot_a_b.png`**
  * **Figure 7**: Explanatory data visualization of the relationship among `Mean Pay Amount`, `Mean Bill Amount`, and Credit Limit Tier. The color gradient represents the Credit Limit Tier, while the black line indicates the LOWESS smoothing curve (using a window of 70% of the data points).
* **`newplot.png`**
  * **Figure 8**: Plotly figure illustrating the relationship between `Mean Pay Amount` and `Max Bill Amount`, categorized by Default Payment Status (color) and Credit Limit Tier (shape). The red curve represents the LOWESS smoothing curve for Defaulters, while the blue dotted curve represents the LOWESS smoothing curve for Non-Defaulters. *(Note: Please disregard the "1, NA" entries in the legend, as they are a rendering artifact).*


---
## 🛠️ Tech Stack & Environment
This project relies on modern R Markdown rendering, advanced visualization grid styling, and interactive dashboard dependencies.

```r
# Core Data Processing & Utilities
library(tidyverse)
library(scales)
library(knitr)

# Static & Advanced Visualizations
library(ggplot2)
library(GGally)
library(patchwork)
library(cowplot)

# Interactive Dashboard Operations
library(plotly)
library(htmlwidgets)
library(htmltools)

# Verify local package versions
packageVersion("tidyverse")
packageVersion("patchwork")
packageVersion("cowplot")
packageVersion("scales")
packageVersion("knitr")
packageVersion("ggplot2")
packageVersion("GGally")
packageVersion("plotly")
packageVersion("htmlwidgets")
packageVersion("htmltools")
```

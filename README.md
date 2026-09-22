# Taiwan Credit Card Default Risk Analytics (R)

An exploratory data analysis (EDA) and advanced visualization project in R investigating customer default payments in Taiwan. Using a dataset of 30,000 credit clients, this project isolates key financial drivers across different credit limit tiers and leverages interactive visualization techniques to uncover indicators of financial distress and default risk.

🔗 **[Live Project Interactive Dashboard](https://github.io)**

---

## 📌 Project Overview
* **Goal**: Analyze 23 explanatory variables (demographics, credit history, bill scales, and payment amounts) to determine key indicators of credit default risk.
* **Key Findings**: 
  * Isolated `Max Bill Amount` and `Mean Pay Amount` as the primary financial drivers across all credit limit tiers.
  * Individuals with a higher `Max Bill Amount` and `Mean Pay Amount` are likely to have a higher Credit Limit Tier. 
  * Individuals classified as High or Very High Credit Limit Tier and Non-Defaulters have significantly higher `Mean Pay Amount` and `Max Bill Amount` compared to Defaulters. 
  * Those with a lower `Mean Pay Amount` are consistently more likely to be Defaulters.
* **Methodology**: Multi-stage data exploration utilizing Principal Component Analysis (PCA) for feature screening, scatter/sine plots for initial trends, and LOESS-smoothed curves to capture the relationship between `Mean Pay Amount` and `Max Bill Amount`.

---

## 📊 Visualizations & Artifacts
The analysis code generates several analytical assets (saved as `.png` files in the repository root) to illustrate findings. All primary plots are designed to be color-blind friendly:

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

## 💾 Dataset Information
This project utilizes the classic **Default of Credit Card Clients Dataset** sourced from the UCI Machine Learning Repository.

* **Source URL**: [UCI Machine Learning Repository - Dataset 350](https://uci.edu)
* **Original Publication**: Yeh, I., & Lien, C. (2009). The comparisons of data mining techniques for the predictive accuracy of probability of default of credit card clients. *Expert Systems with Applications*, 36, 2473-2480. [DOI Link](https://doi.org)
* **Volume**: 30,000 instances, 23 features, 0 missing values.
* **Variables Extracted**:
  * **Demographics**: Credit limit (`LIMIT_BAL`), `SEX`, `EDUCATION`, `MARRIAGE`, `AGE`.
  * **Repayment History**: Past monthly tracking records (`PAY_0` to `PAY_6`) from April to September 2005.
  * **Statements & Payments**: Monthly bill statement amounts (`X12-X17`) and previous payment values (`X18-X23`).
  * **Target Variable**: Binary response indicator (`1` = Default; `0` = No Default).

---

## 🛠️ Tech Stack & Environment
This project relies on modern R Markdown rendering and interactive dashboard dependencies.

```r
# Core environment dependencies
library(htmltools)
library(plotly)
library(ggplot2)
library(dplyr)

# Check htmltools runtime versions
packageVersion("htmltools")
```

### Repository Structure
* **`R_project.Rmd`**: Main R Markdown workbook housing data preprocessing, PCA calculations, analytics pipelines, and Plotly dashboard configurations.
* **`index.html`**: Compiled interactive web output mapped for automatic hosting via GitHub Pages.

---

## 🚀 Getting Started Locally

1. **Clone the repository:**
   ```bash
   git clone https://github.com
   cd r-visualization-project
   ```

2. **Setup R Environment:**
   Open an R session or RStudio and ensure you have the vital packages installed:
   ```r
   install.packages(c("rmarkdown", "htmltools", "plotly", "ggplot2", "dplyr", "tidyverse"))
   ```

3. **Rebuild or Modify:**
   Open `R_project.Rmd` in RStudio and select **Knit** to run the processing scripts and compile a new `index.html` locally.

---

## 📄 License
This project is built using dataset schemas distributed under the **Creative Commons Attribution 4.0 International (CC BY 4.0)** license. You are free to share, copy, adapt, and remix these analytics materials provided appropriate citation credit is passed back to the creators.

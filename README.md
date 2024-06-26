# Digital Nudge Experiment Analysis

This repository contains an R script for analyzing data retrieved from Google BigQuery to measure the effects of digital nudges on user behavior. The goal is to investigate the impact of different digital interventions on user engagement and consumption of specific types of information, and to model the data to find the best fitting statistical model.

### Prerequisites

To run the scripts in this repository, you will need:

- R (version 3.6 or later)
- RStudio (optional, but recommended)
- Google Cloud SDK
- BigQuery API enabled on your Google Cloud project

### Required R Packages

The following R packages are required:

- `bigrquery`
- `dplyr`
- `ggplot2`
- `patchwork`
- `flexplot`
- `cowplot`
- `MASS`
- `mediation`
- `cplm`
- `tweedie`
- `statmod`
- `car`

You can install these packages using the following commands in R:

```r
install.packages(c("bigrquery", "dplyr", "ggplot2", "patchwork", "flexplot", "cowplot", "MASS", "mediation", "cplm", "tweedie", "statmod", "car"))
```

### Configuration

Before running the analysis, you need to configure your connection to Google BigQuery. This involves setting up cookies and custom dimensions and parameters in Google BigQuery. Update the placeholders in the script with your specific project, dataset, and billing information:
```r
project_id = "<project_id>"
dataset_id = "<dataset_id>"
billing_id = "<billing_id>"
```

### Script Overview

The main R script performs the following steps:

1.	Configuration: Connect to Google BigQuery using the bigrquery package.
2.	Data Loading: Retrieve various datasets from Google BigQuery, including session data, experiment case data, time spent in the producer, engagement time, time in the experiment modal, add to cart data, begin checkout data, and purchase data.
3.	Data Wrangling: Process and clean the data to ensure it’s suitable for analysis. This includes handling missing values, summarizing data, and joining datasets into a single dataframe.
4.	Data Filtering: Filter the data based on specific criteria such as country and date range.
5.	Exploratory Data Analysis (EDA): Visualize the data to understand the distribution and relationships between different variables.
6.	Modeling: Fit various statistical models to the data to determine which model best describes the user behavior. This includes Gaussian, Gamma, Poisson, and Tweedie models.
7.	Hypothesis Testing: Perform hypothesis tests to determine the significance of the digital interventions.

### Running the Script

To run the script, open it in RStudio or any R IDE and execute the code. Ensure that you have configured the Google BigQuery connection and installed the required packages.

### Visualization and Analysis

The script includes various visualizations to help understand the data distribution and model fits. The flexplot and ggplot2 packages are used to create these visualizations. Key plots include:

* Histograms and Q-Q plots of time spent in the producer.
* Scatter plots of the number of sessions and value of purchases.
* Boxplots comparing different experiment cases.

Contribution

Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

License

This project is licensed under the MIT License.

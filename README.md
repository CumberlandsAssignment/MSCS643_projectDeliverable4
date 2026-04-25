# MSCS634 Project Deliverable 4: Final Insights, Recommendations, and Presentation

## Project Overview
This final deliverable consolidates the full Advanced Data Mining project completed across Deliverables 1-3. The project uses the Diamonds dataset to analyze how diamond characteristics such as carat, cut, color, clarity, depth, table, and physical dimensions relate to market price and price tier.

## Dataset
The Diamonds dataset contains 53,940 records and 10 attributes: `carat`, `cut`, `color`, `clarity`, `depth`, `table`, `price`, `x`, `y`, and `z`. It was chosen because it is large enough for meaningful modeling, includes both numerical and categorical variables, and supports regression, classification, clustering, and association rule mining.

## Project Steps
1. **Data preparation and EDA:** loaded the data, reviewed structure and summary statistics, confirmed no missing values, removed 146 duplicate records, and explored distributions and correlations.
2. **Feature engineering:** encoded categorical attributes, created derived variables such as diamond volume and log-transformed variables, and created a `price_tier` classification target.
3. **Regression modeling:** built and evaluated regression models to predict diamond price, with carat/volume and quality grades emerging as important predictors.
4. **Classification:** developed Decision Tree and KNN models to predict price tier. The tuned Decision Tree achieved about 98.9% weighted F1, while KNN achieved about 98.5% weighted F1.
5. **Clustering:** applied K-Means clustering using engineered numeric and encoded quality features. The elbow method supported k=4 as a useful segmentation choice.
6. **Association rule mining:** used FP-Growth on cut, color, clarity, and price tier to identify interpretable quality-price patterns.

## Major Findings
- Carat weight and derived volume are the strongest drivers of price.
- Price is highly right-skewed, so log transformation improves modeling stability.
- Cut quality alone is less predictive than combinations of carat, clarity, and color.
- High clarity and top color grades are strongly associated with high price tiers.
- Simpler classification models can perform very well when the target is engineered from price thresholds.

## Practical Recommendations
- Buyers should evaluate carat together with clarity and color rather than relying only on cut labels.
- Sellers can use tier-based classification to organize inventory and flag premium stones.
- Regression models can support price screening, but predictions should be reviewed for unusually large or rare stones.
- Future work should validate models on external market data and include certificate/lab, geographic, and time-based pricing factors.

## Repository Contents
- `notebooks/deliverable4_final_project.ipynb` - consolidated notebook with commented code and visualizations.
- `report/MSCS634_Deliverable4_Final_Report.docx` - comprehensive written report.
- `report/MSCS634_Deliverable4_Final_Report.pdf` - PDF version of the report.
- `slides/MSCS634_Deliverable4_Presentation.pptx` - 5-7 minute presentation slides.
- `images/` - visualization assets used in the report and presentation.

## Ethical Considerations
The dataset does not contain direct personal identifiers, but ethical considerations remain important. Potential concerns include market bias in historical price data, model overreliance on price-derived labels, fairness in consumer-facing pricing, and limited generalizability beyond the dataset source. The project addresses these concerns by documenting assumptions, using interpretable models and visuals, and recommending external validation before production use.

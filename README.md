# Coastal Palaeocliff Mapping with Machine Learning

**Python · QGIS · Random Forest · Support Vector Machine (SVM)**

Academic group project investigating the identification and mapping of palaeocliffs along the Cilento coast (southern Italy, from Capo Palinuro to Cala Cefalo), combining GIS-derived terrain features with supervised classification.

## My contribution

I independently developed the **entire Python analysis pipeline**, including data cleaning, exploratory analysis, model preparation, training and evaluation of Random Forest and SVM classifiers, and export of predictions for QGIS. GIS data preparation and cartographic work were collaborative group activities.

## Workflow

1. Prepare GIS-derived features: elevation, roughness, slope, dissection, surface area ratio, distance and lithology.
2. Load and clean the training and prediction datasets.
3. Explore feature distributions and split the labelled data into training and test sets.
4. Standardize input features for the SVM model.
5. Train Random Forest and SVM classifiers and compare performance.
6. Export probability predictions with spatial coordinates for visualization in QGIS.

## Reported results

| Metric | Random Forest | SVM |
| --- | ---: | ---: |
| Accuracy | 0.98 | 0.89 |
| Precision | 0.96 | 0.82 |
| Recall | 1.00 | 0.98 |
| ROC AUC | 0.998 | 0.981 |

*Values are from the original university presentation/notebook outputs, not an independently re-executed benchmark. A random train/test split on geospatial data may overestimate performance on geographically independent regions.*

## Files

- `paleocliffs_analysis.ipynb`: analysis and modelling notebook (original code with a small non-destructive fix to the target-column selection).
- `dataset_training.csv`: labelled training data (publish only if you are authorized to share these data).
- `requirements.txt`: Python packages used.
- `dataset_finale.csv`: **not included** due to its large size (~90 MB); needed for whole-area predictions and GIS export.

## How to run

1. Open `paleocliffs_analysis.ipynb` in Google Colab or Jupyter.
2. Make `dataset_training.csv` available in the notebook working directory.
3. If authorized to access the original prediction dataset, place `dataset_finale.csv` in the same directory. It must use `;` delimiters and comma decimals, and include coordinate columns `x` and `y`.
4. Install the packages listed in `requirements.txt` (in Colab, most are already installed).
5. Run the notebook cells in order.

**Note:** In Google Colab, upload the files into the session or adapt the file paths to Google Drive. The notebook as provided needs `dataset_finale.csv` even to complete its initial data-loading cell; without it, the full notebook cannot run as-is.

## Collaboration and attribution

University group project. Python implementation by Davide Passariello; GIS and presentation work developed collaboratively.

## Project status

Academic demonstration. Results should not be interpreted as a validated geological survey or independent-area prediction accuracy.

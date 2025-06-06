
# LC-MS Activity Classifier Pipeline

This repository provides a complete pipeline for training, evaluating, and visualizing machine learning models to classify activity states (active, inactive, questionable) from LC-MS (Liquid Chromatography–Mass Spectrometry) data. It includes utilities for model selection, feature visualization, and result reporting.

## 📁 Repository Structure

```
.
├── activity_constants.py          # Configuration and constants
├── data_training.ipynb           # Raw data preparation & transformation
├── training_study.ipynb          # Model training and evaluation pipeline
├── LCMS_visualization.ipynb      # Feature map visualization of trained models
├── reporting.ipynb               # Export results and performance summaries
└── README.md                     # This documentation
```

## 🚀 How to Use

### 1. **Data Preparation**
Use `data_training.ipynb` to:
- Load and pre-process raw LC-MS data
- Organize datasets into training, validation, and test splits
- Ensure data is reshaped into a standard format (up to 1351 columns × 300 rows per sample)

> Dataset folders and parameters are defined in `activity_constants.py`.

### 2. **Model Training and Selection**
Run `training_study.ipynb` to:
- Train multiple models across different architectures and hyperparameters
- Automatically evaluate and select the best-performing model
- Save models to the `Model/` directory

### 3. **Feature Visualization**
Once the best model is selected, use `LCMS_visualization.ipynb` to:
- Visualize learned feature maps and activation patterns
- Compare class separability in reduced-dimensional spaces (e.g., t-SNE or PCA)
- Interpret model behavior on LC-MS data

### 4. **Result Reporting**
Generate structured outputs with `reporting.ipynb`:
- Export predictions to `.csv`
- Include performance metrics (accuracy, confusion matrix, etc.)
- Support for automated summaries per sample or class

## 🔧 Configuration

Modify `activity_constants.py` to:
- Set data directory paths (`data_set_folder`, `model_folder`, etc.)
- Define class thresholds: `max_inactive_value`, `max_quest_value`, `max_active_value`
- Specify dataset partition folders: `training`, `validation`, `test`

## 📊 Output

- Trained models: saved in `/Model/`
- Visualizations: in interactive notebook cells (can be exported)
- CSV reports: per class and overall model performance

## 📦 Dependencies

Ensure you have the following libraries installed (typical requirements include):
```bash
numpy
pandas
matplotlib
scikit-learn
tensorflow or pytorch (depending on model type)
```

Use `pip install -r requirements.txt` if a list is maintained.

## 🧪 Example Use Case

1. Populate the `ModelDataset/` folder with LC-MS formatted data.
2. Run `data_training.ipynb` to prepare input arrays.
3. Execute `training_study.ipynb` to train and evaluate.
4. Use `LCMS_visualization.ipynb` to interpret model internals.
5. Generate exportable results via `reporting.ipynb`.

## 📬 Contact

For issues, contributions, or suggestions, feel free to open an issue or pull request.

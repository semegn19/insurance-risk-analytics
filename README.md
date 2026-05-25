# insurance-risk-analytics

## Reproducing the Data Pipeline

This project uses DVC (Data Version Control) to manage and reproduce the insurance datasets.

### 1. Clone the Repository

```bash
git clone https://github.com/semegn19/insurance-risk-analytics.git
cd insurance-risk-analytics
````

### 2. Install Dependencies

```bash
pip install -r requirements.txt
pip install dvc
```

### 3. Pull the Data from DVC Remote Storage

```bash
dvc pull
```

This command downloads the tracked datasets (raw and processed) from the configured DVC remote storage.

### 4. Run the Data Processing / Analysis

Open the notebook or run the analysis scripts:

```bash
jupyter notebook
```

or

```bash
python src/data_processing.py
```

### 5. Verify Pipeline Status

```bash
dvc status
```
    
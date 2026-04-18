# AI Agent Instructions for CIUS Social Media Analysis Project

## Project Overview
This project analyzes the Canadian Internet Use Survey (CIUS) dataset focusing on social media usage and mental health correlations. The main components are:

- Data processing pipeline in `CIUS_Social_Media_EDA.ipynb`
- Raw data in `Data/Data/cius_pumf.sas7bdat`
- Cleaned datasets: 
  - `CIUS_SocialMedia_16cols_CLEAN.csv` (numeric codes)
  - `CIUS_SocialMedia_Clean_Labeled.csv` (human-readable labels)

## Key Workflows

### 1. Data Loading
```python
# Use pathlib to locate SAS data file robustly
from pathlib import Path
root = Path.cwd()
file_path = next(root.rglob("cius_pumf.sas7bdat"))
df = pd.read_sas(str(file_path), format="sas7bdat", encoding="latin1")
```

### 2. Data Cleaning Conventions
- Keep only 16 specific columns related to social media usage
- Use Int64 dtype for categorical codes before filtering
- Preserve 'Weight' column without filtering
- Validate against defined valid_ranges for each column
- Convert numeric codes to human-readable labels using label_mappings

### 3. Column Naming Standards
Original CIUS column names are transformed using consistent patterns:
- Remove underscores from survey codes (e.g., 'AGE_GRP' → 'Age')
- Use Title Case for demographic variables
- Use underscores for compound features (e.g., 'Income_Group')

### 4. Visualization Conventions
- Use seaborn with "whitegrid" style
- Standard figure sizes: 
  - (8,4) for horizontal bar charts
  - (6,4) for vertical bar charts
- Consistent axis labeling:
  - Remove redundant axis labels when obvious
  - Empty strings for categorical axes

## Key Dependencies
- pandas (for data manipulation)
- seaborn & matplotlib (for visualization)
- sas7bdat (for reading SAS files)

## Project Structure Notes
- Keep intermediate CSV files in project root for easy access
- Documentation and layouts organized in respective subdirectories
- All data cleaning and analysis in single notebook for reproducibility

## Common Tasks
- To add new visualizations: Follow seaborn style conventions in EDA section
- To modify data cleaning: Update valid_ranges and label_mappings dictionaries
- To extend analysis: Add new sections after existing EDA cells
# Practical Data Science - AI Coding Agent Instructions

## Operational Context

When editing or creating notebooks, always edit and generate cells one by one. You should also run cells often to verify correctness.

When editing notebook cells or creating a new Jupyter notebook, do not create large cells. Each cell in a notebook should do one thing well.

When trying to interact with the notebook, you should avoid using terminal tools. Always try to see if the interaction can be done inside the notebook itself.

When faced with import errors, first check if there is an existing cell that imports the module in question.


## Project Structure

### Assignment Work (`A1/`)

- `assignment1_TEMPLATE.ipynb`: Main submission template with structured task sections
- `READ_ME.md`: Task requirements (151 lines, read carefully before starting)
- `RUBRIC.md`: Grading criteria - emphasizes error-free data, appropriate visualizations, clear explanations
- `DB_FEATURES.md`: Complete dataset feature descriptions with types, roles, and valid ranges
- **Data files**:
  - `student-data-25s3.csv`: Primary dataset (Student Performance from UCI ML Repository)
  - MovieLens 100K (`u.data`, `u.item`) for Task 4 external data merge
- **Output files**: `student_fix1.csv`, `student_fix2.csv`, `report.pdf`

## Code Conventions

### Data Cleaning Pattern (Task 1 Standard)

```python
# 1. Load data
df = pd.read_csv('data/student_data_25s3.csv')

# 2. Check equivalence (row/column counts, dtypes)

# 3. Clean in this order:
# - Strip whitespace: df['col'] = df['col'].str.strip()
# - Fix typos (case-sensitive)
# - Sanity checks (age >= 0, valid ranges)
# - Handle missing values LAST
```

### Missing Values - Multiple Approaches Required (Task 3.1)

- Generate **separate CSV files** for each approach:
  - `student_fix1.csv`: Mean imputation (column-wise)
  - `student_fix2.csv`: Median imputation (column-wise)
- Use `fillna()` with appropriate aggregation functions
- Document impact on visualizations

### Visualization Requirements

- **Always include titles, axis labels** for every plot
- Task 2.1: Select 1 nominal + 1 ordinal + 1 numerical variable
- Task 2.2: 3 hypothesis-driven visualizations (pairs of columns)
- Task 2.3: Scatter matrix for numerical columns only
- Use `sns.catplot()`, `plt.subplots()`, `pd.plotting.scatter_matrix()`

## Assignment Submission Rules

### File Naming (Case-Sensitive)

- Template notebook → student ID-based naming
- Generated CSV files → exact names: `student_fix1.csv`, `student_fix2.csv`
- Report → `report.pdf` (generated from Jupyter markdown cells)

### Code Documentation

- **One-line comments required** before each logical block
- Examples: "# load data", "# check typos", "# handle missing values"
- Explain choices and list modified data rows explicitly

## Testing & Validation

### Common Errors to Check

- **Syntax errors in notebooks**: Use Pylance file syntax checker
- **Import errors**: Verify all required packages installed in active environment
- **Operator precedence**: Always parenthesize boolean conditions with `&`, `|`
- **Path separators**: Use forward slashes `/` or raw strings `r"path\to\file"` for cross-platform compatibility

### Data Quality Checks

1. Typos (case variations, spelling)
2. Extra whitespace (leading/trailing/internal)
3. Sanity checks (impossible values: age < 0, invalid ranges)
4. Missing values (check with `df.isna().sum()`)
5. Outliers (use IQR, quantiles, visualization)

## Dataset Domain Knowledge (A1)

### Student Performance Dataset

- **Source**: UCI ML Repository - Portuguese secondary school students
- **Context**: Student achievement in Math/Portuguese courses
- **Key features** (see `A1/DB_FEATURES.md` for full details):
  - **Demographics**: age (15-22), sex, address (urban/rural)
  - **Family**: parent education (Medu/Fedu: 0-4 scale), jobs, cohabitation status
  - **School**: school choice (GP/MS), travel time, study time, past failures
  - **Social**: romantic relationship, going out, alcohol consumption (Dalc/Walc: 1-5)
  - **Support**: school support, family support, paid classes, activities
  - **Targets**: G1, G2, G3 (grades 0-20)


## Grading Emphasis (from RUBRIC.md)

### What Gets High Marks

- **Error-free data preparation**: "completely free from errors" in Task 1
- **Appropriate visualizations**: Graphs with all necessary elements (titles, labels, formatting)
- **Clear hypotheses**: Concisely stated, plausible hypotheses for Task 2.2
- **Comprehensive discussion**: Clear, insightful analysis of relationships (or lack thereof)
- **Proper missing value handling**: Identify, discuss impact, reasonably replace/remove

### Common Grading Deductions

- Missing/incomplete analyses
- Inappropriate or missing graphs
- Unclear or missing explanations/hypotheses
- Incorrect formatting (missing titles, labels, legends)
- Errors in data preparation (typos, whitespace, invalid values not fixed)

## Key Insights for Agents

- **Read feature descriptions first**: Check `A1/DB_FEATURES.md` to understand valid ranges before cleaning
- **Assignment context matters**: Understand Task 1-5 structure from `READ_ME.md` before suggesting code
- **Multiple solutions expected**: Task 3 specifically requires comparing different approaches
- **Hypothesis-driven analysis**: Don't just plot - explain the "why" behind each visualization
- **No library restrictions**: All standard data science libraries (pandas, numpy, matplotlib, seaborn, plotly, sklearn) are allowed
- **PowerShell quirks**: Windows terminal commands differ significantly from bash/zsh
- **Virtual environment critical**: Always configure Python environment before running code or installing packages

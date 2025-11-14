## Operational Context

When editing or creating notebooks, always edit and generate cells one by one. You should also run cells often to verify correctness.

When editing notebook cells or creating a new Jupyter notebook, do not create large cells. Each cell in a notebook should do one thing well.

When trying to interact with the notebook, you should avoid using terminal tools. Always try to see if the interaction can be done inside the notebook itself.

When faced with import errors, first check if there is an existing cell that imports the module in question.


## Project Structure
- `DB_FEATURES.md`: Complete dataset feature descriptions with types, roles, and valid ranges


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

### Code Documentation

- **One-line comments required** before each logical block
- Examples: "# load data", "# check typos", "# handle missing values"
- Explain choices and list modified data rows explicitly


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

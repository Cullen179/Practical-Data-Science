# Practical Data Science

This repository contains data science assignments and tutorials for RMIT University coursework.

## 📁 Project Structure

```
.
├── A1-specification-data/          # Assignment 1 files
│   ├── assignment1_TEMPLATE.ipynb  # Main assignment notebook
│   ├── student-data-25s3.csv       # Student performance dataset
│   └── Assignment1_Specification_25S3.pdf
├── complete-pandas-tutorial/       # Pandas learning materials
│   ├── tutorial.ipynb
│   └── data/
├── learn/                          # Practice notebooks
│   ├── eda/                        # Exploratory Data Analysis
│   └── visual/                     # Data Visualization
└── requirements.txt                # Python dependencies
```

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- pip package manager
- Jupyter Notebook or VS Code with Jupyter extension

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/Cullen179/Practical-Data-Science.git
   cd Practical-Data-Science
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   # Windows
   python -m venv venv
   .\venv\Scripts\activate

   # macOS/Linux
   python3 -m venv venv
   source venv/bin/activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook**
   ```bash
   jupyter notebook
   ```
   Or open the notebooks directly in VS Code.

## 📊 Assignment 1: Student Performance Analysis

The main assignment notebook (`assignment1_TEMPLATE.ipynb`) includes:

- **Data Preparation**: Loading and cleaning student performance data
- **Exploratory Data Analysis**: Statistical analysis and data profiling
- **Data Visualization**: Creating insightful visualizations
- **Feature Analysis**: Understanding categorical and numerical features

### Key Features Analyzed

- **Demographics**: Age, sex, address (urban/rural)
- **Family**: Family size, parent education, parent jobs
- **Academic**: Study time, failures, educational support
- **Social**: Free time, going out, romantic relationships
- **Health**: Health status, alcohol consumption
- **Performance**: Grades (G1, G2, G3), absences

## 🔧 Data Cleaning Process

The notebook implements comprehensive data cleaning:

1. **Typo Correction**: Fixing character replacements (e.g., 'O' → '0' in age)
2. **Invalid Value Removal**: Filtering out impossible values
3. **Range Validation**: Ensuring numeric values are within specified ranges
4. **Categorical Validation**: Checking against allowed categories
5. **Duplicate Removal**: Eliminating duplicate records
6. **Whitespace Trimming**: Cleaning string data
7. **Missing Value Handling**: Detecting and handling missing data

## 📦 Dependencies

Main packages used:
- `pandas`: Data manipulation and analysis
- `numpy`: Numerical computing
- `matplotlib`: Data visualization
- `seaborn`: Statistical data visualization
- `ydata-profiling`: Automated EDA reports
- `plotly`: Interactive visualizations

## 📝 Usage

### Running the Assignment Notebook

1. Navigate to the assignment folder:
   ```bash
   cd A1-specification-data
   ```

2. Open the notebook:
   ```bash
   jupyter notebook assignment1_TEMPLATE.ipynb
   ```

3. Run cells sequentially or use "Run All" from the Cell menu

### Generating Data Reports

The notebook includes automated profiling:
```python
from ydata_profiling import ProfileReport
profile = ProfileReport(df, title="Student Profile")
profile.to_file("student_report.html")
```

## 🤝 Contributing

This is a personal academic project. If you're a fellow student:
- Feel free to fork for your own learning
- Please don't copy assignments directly (academic integrity)
- Suggestions and improvements are welcome via issues

## 📄 License

This project is for educational purposes as part of RMIT University coursework.

## 👤 Author

**Student ID**: s1234567 (Update with your actual ID)
**Course**: Practical Data Science
**Institution**: RMIT University
**Semester**: 2025 S3

## 📮 Contact

For questions or collaboration:
- Create an issue in this repository
- Email: [Your RMIT Email]

## 🎓 Acknowledgments

- RMIT University for course materials
- Dataset source: Student Performance Dataset
- Teaching staff for guidance and support

---

**Note**: This repository contains coursework. Please respect academic integrity policies.

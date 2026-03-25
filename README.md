# Customer Behavior Analysis in Online Retail

## Project Overview

This repository contains a comprehensive data science project that analyzes customer purchasing behavior in an online retail context. Using exploratory data analysis (EDA) and machine learning techniques, we uncover valuable patterns and segments in customer data to drive business decisions.

The project demonstrates the full data science workflow: from data cleaning and feature engineering, through exploratory analysis, to advanced clustering techniques.

---

## Dataset Description

**Dataset**: Online Retail Transaction Data  
**Format**: CSV  
**Features**:
- `InvoiceNo`: Unique identifier for each transaction
- `StockCode`: Product identifier
- `Description`: Product name/description
- `Quantity`: Number of units purchased
- `InvoiceDate`: Transaction date and time
- `UnitPrice`: Price per unit
- `CustomerID`: Unique customer identifier
- `Country`: Customer country
- `TotalPrice`: Total transaction value (derived)

**Data Preprocessing**:
- Removed null CustomerID entries
- Filtered out zero/negative quantities and prices
- Removed duplicate records
- Converted dates to datetime format
- Engineered TotalPrice feature

---

## Workflow Steps

### 1. **Data Loading & Cleaning**
   - Load the online retail dataset
   - Handle missing values and outliers
   - Remove invalid transactions (negative quantities/prices)
   - Ensure data quality and consistency

### 2. **Exploratory Data Analysis (EDA)**
   - Analyze sales distribution across countries
   - Identify top products and customers
   - Examine monthly sales trends
   - Study correlation between key variables
   - Visualize customer purchasing patterns

### 3. **RFM Segmentation**
   - Calculate Recency, Frequency, and Monetary metrics
   - Create customer RFM profiles
   - Analyze distributions and statistical summaries

### 4. **Machine Learning: K-Means Clustering**
   - Normalize RFM features using StandardScaler
   - Apply K-Means clustering (k=3)
   - Segment customers into three groups:
     - **High-Value Customers**: Frequent purchases, high spending
     - **Regular Customers**: Moderate purchase frequency and spending
     - **Low-Value Customers**: Infrequent purchases, low spending

### 5. **Advanced Visualization**
   - 2D customer segmentation scatter plots
   - 3D visualization of RFM clusters
   - Heatmaps and distribution plots
   - Save visualizations for presentations and reports

---

## Technologies Used

| Technology | Purpose |
|-----------|---------|
| **Python 3.8+** | Programming language |
| **Pandas** | Data manipulation and analysis |
| **NumPy** | Numerical computing |
| **Matplotlib** | Static visualization |
| **Seaborn** | Statistical visualization |
| **Plotly** | Interactive visualization |
| **Scikit-learn** | Machine learning (K-Means clustering) |
| **Jupyter Notebook** | Interactive analysis environment |

---

## Machine Learning Method: K-Means Clustering

### What is K-Means?

K-Means is an unsupervised machine learning algorithm that partitions data into k clusters by:
1. Initializing k random centroids
2. Assigning each point to the nearest centroid
3. Recalculating centroids based on cluster assignments
4. Repeating until convergence

### Application to RFM Analysis

**Advantages**:
- Automatically segments customers without predefined labels
- Scales well to large datasets
- Produces interpretable clusters
- Identifies actionable customer segments

**Our Implementation**:
- **Features**: Recency, Frequency, Monetary (normalized)
- **K (clusters)**: 3
- **Random state**: 42 (for reproducibility)

**Cluster Characteristics**:
```
Cluster 0 (High-Value):   Low recency, High frequency, High monetary
Cluster 1 (Regular):      Medium recency, Medium frequency, Medium monetary
Cluster 2 (Low-Value):    High recency, Low frequency, Low monetary
```

---

## Business Insights

### Key Findings

1. **Concentration of Revenue**: 
   - A small percentage of customers (Cluster 0) contribute disproportionately to total revenue
   - Focus retention efforts on high-value customers

2. **Frequency-Monetary Relationship**:
   - Strong positive correlation between purchase frequency and spending
   - Encouraging repeat purchases increases revenue

3. **Geographic Patterns**:
   - UK dominates sales, followed by Netherlands, EIRE, Germany
   - Opportunity to expand in emerging markets

4. **Product Insights**:
   - Few bestselling products drive majority of sales
   - Stock management should focus on top performers

5. **Customer Lifecycle**:
   - High-frequency customers have lower recency (more active)
   - Implement re-engagement campaigns for inactive customers

---

## Business Recommendations

### For High-Value Customers (Cluster 0)
- ✅ Implement premium loyalty programs
- ✅ Offer exclusive early access to new products
- ✅ Provide personalized customer support
- ✅ Create VIP tiers with special benefits

### For Regular Customers (Cluster 1)
- 📈 Encourage more frequent purchases through promotional campaigns
- 📈 Recommend complementary products
- 📈 Offer subscription or bulk purchase discounts
- 📈 Maintain regular communication via newsletters

### For Low-Value Customers (Cluster 2)
- 🔄 Launch win-back campaigns with special offers
- 🔄 Survey to understand purchase barriers
- 🔄 Provide targeted discounts on popular items
- 🔄 Simplify checkout process to reduce friction

### Overall Strategies
- 🎯 Use segmentation for targeted email marketing
- 🎯 Develop tailored product recommendations per segment
- 🎯 Monitor cluster migrations to track customer lifecycle
- 🎯 Adjust inventory based on segment preferences

---

## Project Structure

```
Customer-Behavior-Analysis/
│
├── data/
│   └── online_retail.csv              # Raw transaction data
│
├── notebook/
│   └── Customer_Behavior_Analysis.ipynb  # Main analysis notebook
│
├── images/
│   ├── sales_by_country.png           # Top 10 countries by revenue
│   ├── top_products.png               # Top 10 products
│   ├── correlation_heatmap.png        # Feature correlations
│   ├── kmeans_clusters.png            # 2D cluster visualization
│   └── customer_3d_clusters.png       # 3D cluster visualization
│
├── README.md                          # This file
├── requirements.txt                   # Python dependencies
└── .gitignore                         # Git ignore patterns
```

---

## Installation & Setup

### Prerequisites
- Python 3.8 or higher
- pip or conda package manager
- Git

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/Customer-Behavior-Analysis.git
cd Customer-Behavior-Analysis
```

### Step 2: Create a Virtual Environment (Optional but Recommended)
```bash
# Using venv
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Or using conda
conda create -n customer-analysis python=3.9
conda activate customer-analysis
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Launch Jupyter Notebook
```bash
cd notebook
jupyter notebook Customer_Behavior_Analysis.ipynb
```

---

## Running the Analysis

1. **Open the Jupyter Notebook**:
   - Navigate to the notebook directory
   - Run `jupyter notebook` or `jupyter lab`
   - Open `Customer_Behavior_Analysis.ipynb`

2. **Execute Cells Sequentially**:
   - First cell: Imports the required libraries
   - Data loading and cleaning cells
   - Exploratory analysis cells
   - K-Means clustering cells
   - Visualization and insight cells

3. **View Results**:
   - All visualizations display inline in the notebook
   - Saved images are stored in the `images/` folder
   - Statistical summaries are printed to cell outputs

4. **Modify & Experiment**:
   - Adjust parameters (e.g., number of clusters)
   - Add new analyses
   - Create additional visualizations

---

## Expected Outputs

After running the notebook, you'll generate:

| Output | Location | Purpose |
|--------|----------|---------|
| Sales by Country Chart | `images/sales_by_country.png` | Revenue distribution visualization |
| Top Products Chart | `images/top_products.png` | Best-selling products ranking |
| Correlation Heatmap | `images/correlation_heatmap.png` | Feature relationships |
| K-Means Clusters | `images/kmeans_clusters.png` | 2D customer segmentation |
| 3D Clusters | `images/customer_3d_clusters.png` | 3D RFM visualization |
| Statistical Reports | Notebook output cells | Detailed numerical analysis |

---

## GitHub Repository Guidelines

### What's Included ✅
- Clean, well-commented Jupyter notebook
- All data files (CSV)
- Generated visualizations (PNG)
- Requirements file for reproducibility
- Comprehensive README documentation

### Viewing on GitHub
When viewing this repository on GitHub:
- The notebook renders automatically with all outputs
- Visualizations display inline
- Code is highlighted with syntax coloring
- Tables and DataFrames format nicely

### Tips for GitHub Users
1. Click on the notebook filename to view it directly
2. GitHub renders Jupyter notebooks natively
3. All charts and images are visible without downloading
4. Large notebooks may take a few seconds to load

---

## Future Improvements

### Analysis Enhancements
- [ ] Implement RFM clustering with custom thresholds instead of K-Means
- [ ] Add seasonal analysis with time-series decomposition
- [ ] Perform customer lifetime value (CLV) prediction
- [ ] Conduct cohort analysis to track customer groups over time

### Machine Learning Extensions
- [ ] Try alternative clustering algorithms (DBSCAN, Hierarchical Clustering)
- [ ] Implement anomaly detection for unusual purchase patterns
- [ ] Build predictive models for customer churn
- [ ] Develop recommendation system using collaborative filtering

### Visualization & Reporting
- [ ] Create interactive Plotly dashboards
- [ ] Add statistical tests (chi-square, ANOVA)
- [ ] Generate automated PDF reports
- [ ] Build Tableau/Power BI visualizations

### Production & Deployment
- [ ] Create Python script version for batch processing
- [ ] Build REST API for cluster prediction
- [ ] Implement real-time customer segmentation
- [ ] Containerize with Docker for reproducibility

---

## How to Reproduce Results

To ensure you get identical results:

1. **Use the exact Python version**:
   ```bash
   python --version  # Should be 3.8+
   ```

2. **Install exact package versions**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Use consistent random seed**:
   - The K-Means model uses `random_state=42`
   - Set NumPy seed if needed: `np.random.seed(42)`

4. **Run cells sequentially**:
   - Don't skip cells
   - Execute from top to bottom
   - Each cell builds on previous outputs

---

## Troubleshooting

### Issue: Module not found error
**Solution**: Install missing packages
```bash
pip install -r requirements.txt
```

### Issue: CSV file not found
**Solution**: Ensure you're running the notebook from the `notebook/` folder
```bash
cd Student-Behavior-Analysis/notebook
jupyter notebook
```

### Issue: Plots not displaying
**Solution**: Add this to your notebook's first cell
```python
%matplotlib inline
import warnings
warnings.filterwarnings('ignore')
```

### Issue: Memory error with large dataset
**Solution**: Process data in chunks or use data sampling
```python
df = pd.read_csv("../data/online_retail.csv", nrows=50000)
```

---

## License

This project is open source and available under the MIT License. Feel free to use, modify, and distribute this code for educational and commercial purposes.

---

## Author

**Project Name**: Customer Behavior Analysis in Online Retail  
**Created**: 2024  
**Purpose**: Demonstrate comprehensive data science workflow from EDA to machine learning  
**Contact**: For questions or contributions, please open an issue on GitHub

---

## Contributing

Contributions are welcome! To contribute:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

---

## References & Resources

### Pandas & Data Science
- [Pandas Documentation](https://pandas.pydata.org/docs/)
- [RFM Analysis Guide](https://en.wikipedia.org/wiki/RFM_(customer_value))

### Machine Learning
- [Scikit-learn K-Means](https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html)
- [K-Means Clustering Tutorial](https://towardsdatascience.com/k-means-clustering-algorithm-applications-evaluation-methods-and-drawbacks-aa03e644b48a)

### Visualization
- [Matplotlib Documentation](https://matplotlib.org/stable/contents.html)
- [Seaborn Gallery](https://seaborn.pydata.org/examples.html)
- [Plotly Documentation](https://plotly.com/python/)

### Best Practices
- [Data Science Workflow](https://www.kdnuggets.com/2018/01/data-science-workflow.html)
- [GitHub README Best Practices](https://www.makeareadme.com/)

---

## Support

If you encounter any issues or have questions:
1. Check the Troubleshooting section above
2. Review the code comments in the notebook
3. Open an issue on GitHub with:
   - Python version (python --version)
   - Error message (full traceback)
   - Steps to reproduce
   - Operating system

---

**Last Updated**: March 16, 2026
**Status**: Complete and Ready for Use ✅


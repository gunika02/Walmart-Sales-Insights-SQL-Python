# Walmart Data Analysis: End-to-End SQL + Python 

## 📌 Project Overview
This project is an **end-to-end data analysis pipeline** for Walmart sales data, combining **Python** for data cleaning and preprocessing with **SQL** for advanced querying and business insights.

The goal is to **simulate a real-world data analyst workflow** — from **data extraction via API**, to **data transformation**, to **loading into databases** (MySQL & PostgreSQL), and finally **executing business-driven SQL analysis**.



---

## 🚀 Key Objectives
- Build a **data pipeline** from raw dataset to database-ready tables.
- Perform **data cleaning, transformation, and feature engineering** using Python.
- Load cleaned data into **MySQL** and **PostgreSQL** for querying.
- Use **SQL** to solve business problems and generate actionable insights.
- Document and publish the project for portfolio use.

---

## 🛠 Tools & Technologies
- **Languages**: Python (Pandas, NumPy), SQL
- **Databases**: MySQL, PostgreSQL
- **Libraries**: `pandas`, `numpy`, `sqlalchemy`, `mysql-connector-python`, `psycopg2`
- **Data Source**: [Kaggle – Walmart Sales Dataset](https://www.kaggle.com/najir0123/walmart-10k-sales-datasets)
- **IDE**: Visual Studio Code (VS Code)
- **Version Control**: Git & GitHub
- **API Access**: Kaggle API for dataset retrieval

---

## 📂 Project Structure
```
|-- data/                      # Raw and cleaned datasets
|-- sql_queries/               # SQL scripts for analysis
|-- notebooks/                 # Jupyter notebooks for Python exploration
|-- main.py                    # Main ETL pipeline script
|-- requirements.txt           # Python dependencies
|-- README.md                  # Project documentation
```
---

## 📊 Project Workflow

### 1) Environment Setup
Install Python 3.8+ and set up a project workspace in VS Code.

```bash
pip install pandas numpy sqlalchemy mysql-connector-python psycopg2
```

### 2) Data Acquisition (Kaggle API)
- Download Kaggle API token (`kaggle.json`) from [Kaggle Account Settings](https://www.kaggle.com/).
- Place token in your local `.kaggle/` directory.
- Fetch dataset:
```bash
kaggle datasets download -d najir0123/walmart-10k-sales-datasets
```

### 3) Data Exploration & Cleaning
- Inspect dataset with `.info()`, `.describe()`, `.head()`.
- Remove duplicates, handle missing values, and ensure correct data types.
- Format currency fields and convert dates to `datetime`.
- **Feature Engineering**: Add `total_amount` column = `unit_price * quantity`.

### 4) Load Data into Databases
- Use SQLAlchemy to connect to MySQL & PostgreSQL.
- Create tables and insert cleaned data.
- Verify data integrity with basic SQL queries.

**Example SQLAlchemy URIs**
```python
mysql_uri = 'mysql+mysqlconnector://USER:PASSWORD@HOST:3306/walmartdb'
pg_uri    = 'postgresql+psycopg2://USER:PASSWORD@HOST:5432/walmartdb'
```

### 5) SQL Analysis: Business Questions
- 📈 Revenue trends by branch and category  
- 🏆 Best‑selling product categories  
- 🕒 Peak sales hours and days  
- 💳 Preferred payment methods  
- 💰 Profit margin analysis by branch & category  

**Example Query – Top 5 Categories by Revenue**
```sql
SELECT category, ROUND(SUM(total_amount), 2) AS revenue
FROM walmart_sales
GROUP BY category
ORDER BY revenue DESC
LIMIT 5;
```

### 6) Documentation & Publishing
- Detailed project write‑up in README & Jupyter notebooks.
- Code and queries pushed to GitHub.

---

## ✅ Getting Started

1. **Clone the repository**
```bash
git clone <your-repo-url>
cd <your-repo-folder>
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Configure Kaggle API** and download the dataset (see above).

4. **Run the pipeline**
```bash
python main.py
```

---

## 📈 Results & Insights (Examples)
> Replace with your findings once you run the analysis.

- **Top Performing Branch**: e.g., *Branch A* shows the highest revenue.
- **Peak Shopping Hours**: e.g., *17:00–20:00* sees the most transactions.
- **Most Popular Payment Method**: e.g., *E‑wallet* leads by share.
- **Best‑Selling Category**: e.g., *Health & Beauty* dominates sales.

---

## 🔮 Future Enhancements
- Build an **interactive dashboard** (Power BI / Tableau / Streamlit).
- Automate ingestion for **real‑time sales tracking**.
- Add **forecasting models** for demand prediction.

---

## 🤝 Contributing
Contributions, issues, and feature requests are welcome!  
Feel free to open an issue or submit a pull request.

---

## 📜 License
This project is licensed under the **MIT License**.

---

## 🙌 Acknowledgments
- **Data Source**: Kaggle – Walmart Sales Dataset
- Inspired by **retail analytics** and **supply chain** case studies.

# ETL Pipeline and Data Warehousing Project

---

## Project Overview

This project demonstrates a complete **End-to-End ETL (Extract, Transform, Load)** pipeline and data warehousing solution. It simulates a retail business scenario where multiple data sources are integrated, cleaned, transformed, and loaded into a PostgreSQL data warehouse for reporting and analytics.

The pipeline handles structured (CSV) and semi-structured (JSON) data, performs data validation and enrichment, and creates relational tables with referential integrity to support business intelligence needs.

---

## ETL Pipeline Overview

- **Staging Tables:** Raw data was first loaded into PostgreSQL staging tables created automatically or from source schemas.
- **Data Transformation:** We performed data cleaning and transformation on the staging tables, including ensuring correct data types and formats.
- **Final Tables:** Transformed data was then loaded into the final warehouse tables designed with appropriate primary keys and foreign key constraints for referential integrity.
- **Views and Reporting:** Views and summary tables were created from these final tables to support business insights and analytics.

---

## Features

- **Extraction** of raw data from multiple source files (CSV and JSON)
- **Data cleaning and transformation** using Python and Pandas
- Handling of **nested JSON to relational tables**
- Validation of **data quality** (duplicates, nulls, formats)
- **Schema design** with primary and foreign key constraints
- **Loading** of cleansed data into PostgreSQL tables
- Creation of **views** for key business metrics:
    - Sales per store
    - Top products by quantity sold
    - Employee count per store
    - Revenue by city

---

## Technologies Used

- **Python** (Pandas, psycopg2)
- **PostgreSQL** with pgAdmin 4
- **SQL** (DDL and DML scripts)
- **CSV and JSON** data files
- **Git and GitHub** for version control

---

## Project Structure

```plaintext
├── ETL.ipynb          # Main Python ETL script for extraction, transformation, and loading
├── ETL_Database.sql       # SQL script for schema creation, inserts, transformations, and views
├── README.md              # Project documentation (this file)

```
## Setup Instructions
### Prerequisites

- Python 3.8+ installed
- PostgreSQL installed and running
- pgAdmin 4 for database management (optional but recommended)
- Git for version control

## 1. Clone the Repository

```bash
git clone [https://github.com/yourusername/your-etl-project.git](https://github.com/yourusername/your-etl-project.git)
cd your-etl-project
```

## 2. Install Dependencies

Before running the ETL script, please ensure you have installed the required Python packages manually:

- pandas
- psycopg2

You can install them using:

```bash
pip install pandas psycopg2
```

## 3. Configure PostgreSQL

- Create a new database (e.g., retail_dw).
- Update connection parameters in ETL.py (host, port, database, user, password).

## 4. Load Database Schema and Data

```bash
psql -U your_username -d retail_dw -f ETL_Database.sql
```
- Note: The ETL_Database.sql file includes the full transformation process, from initial PostgreSQL tables (created during import) to the final schema used for analysis. This includes all necessary DDL and DML operations.

## 5. Running the ETL Pipeline
Execute the Python ETL script to extract, transform, and load the data:

```bash
python ETL.ipynb
```

This script will:
- Read raw CSV and JSON files
- Clean and transform the data
- Load data into the final PostgreSQL tables
- Refresh views for reporting
  
## 6. Sample Queries
Once loaded, you can query the data warehouse tables or views for insights. Examples:

```SQL
-- Total sales by store
SELECT * FROM v_sales_per_store;

-- Top 4 products by quantity sold
SELECT * FROM v_top_products_by_quantity

-- Employee count per store
SELECT * FROM v_employee_count_per_store;

-- Revenue per city
SELECT * FROM v_revenue_per_city;
```

## Contribution
Feel free to fork the repo and contribute enhancements or fixes via pull requests.

## License
This project is licensed under the MIT License.

## Contact
For any questions or feedback, please contact:

- Prosper Amamgbo – amaprosperjr@gmail.com

# Thank you for reviewing this project!

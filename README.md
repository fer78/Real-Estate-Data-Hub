# **Real Estate Data Engineering Project**

## Web Scraping · ETL · SQL Database · Analytics · Dashboards

This project builds a full **data engineering pipeline** to collect, process, store, and analyze real estate listings from online property portals such as Idealista and Fotocasa *(for educational and portfolio purposes only)*.

The goal is to showcase practical skills in:

* Advanced web scraping
* Data cleaning and normalization
* ETL pipeline design
* SQL database modeling
* Exploratory data analysis (EDA)
* Dashboard creation with Power BI / Python
* Clean, modular, production-oriented code

---

## **Key Features**

* Modular scrapers for multiple real estate websites
* Extraction of essential property attributes:

  * Address
  * Price
  * Property type
  * Square meters
  * Bedrooms
  * Bathrooms
  * Floor level
  * Construction year (if available)
  * Description
  * Coordinates (when available)
* Automated ETL pipeline (Python)
* Persistent storage in a SQL database (PostgreSQL or SQLite)
* Notebooks for exploratory analysis
* Power BI dashboards for pricing insights and geographic patterns
* Fully documented and maintainable codebase

> **Real data is NOT included due to legal restrictions.**
> A synthetic dataset is provided for testing and demonstration purposes.

---

##  **Project Architecture**

```
Scrapers (Idealista, Fotocasa)
          │
          ▼
HTML Extraction + Cleaning
          │
          ▼
Normalization + Validation
          │
          ▼
SQL Database (custom schema)
          │
          ▼
Analysis (Python / Power BI)
```

Full architecture diagrams are available in `/docs/arquitectura_pipeline.png`.

---

##  **Repository Structure**

```
/real-estate-data-engineering
│
├── src/
│   ├── scrapers/
│   │   ├── idealista_scraper.py
│   │   └── fotocasa_scraper.py
│   ├── pipelines/
│   │   └── etl_pipeline.py
│   ├── db/
│   │   ├── schema.sql
│   │   └── connection.py
│   └── utils/
│
├── data/
│   ├── synthetic/   ← Synthetic dataset for testing
│   └── raw/         ← Ignored by .gitignore
│
├── notebooks/
│   ├── exploration.ipynb
│   └── price_m2_analysis.ipynb
│
├── dashboards/
│   ├── powerbi/
│   └── python/
│
├── docs/
│   ├── arquitectura_pipeline.png
│   └── database_diagram.png
│
├── .env.example
├── .gitignore
├── LICENSE
└── README.md
```

---

##  **Technologies Used**

### **Scraping**

* Python
* Requests / HTTPX
* BeautifulSoup4 / lxml
* Selenium (optional, for dynamic pages)

### **ETL & Data Processing**

* Pandas
* PyArrow
* Custom validation scripts

### **Database**

* PostgreSQL · SQLite
* SQLAlchemy ORM


## **Database Model (Simplified)**

**Table: properties**

| Field           | Type      | Description              |
| --------------- | --------- | ------------------------ |
| id              | UUID      | Unique identifier        |
| url             | Text      | Original listing URL     |
| address         | Text      | Property address         |
| price           | Numeric   | Price in euros           |
| area_m2         | Integer   | Square meters            |
| bedrooms        | Integer   | Number of bedrooms       |
| bathrooms       | Integer   | Number of bathrooms      |
| type            | Text      | Flat, house, attic, etc. |
| lat             | Float     | Latitude                 |
| lon             | Float     | Longitude                |
| description     | Text      | Listing description      |
| extraction_date | Timestamp | Scraping timestamp       |

Full ER diagram available in `/docs/database_diagram.png`.


## **License**

The code in this project is released under the **MIT License**.
No datasets are published in this repository.

---

## 👤 **Author**

**Fernando Rioseco Rodriguez**
Data Scientist

---

## **Contributions**

Pull requests are welcome—scraper improvements, pipeline optimizations, documentation, or analytics modules.


# Microsoft Fabric – End-to-End Data Engineering Project

## Project Overview

This project demonstrates a full end-to-end data engineering pipeline built on Microsoft Fabric, following real-world enterprise data architecture patterns.

The solution covers the complete lifecycle:

- Raw data ingestion  
- Data transformation  
- Incremental data processing (CDC-style)  
- Analytical data modeling  
- Warehouse loading for reporting and Power BI consumption  

The architecture follows the **Bronze → Silver → Gold** design pattern.

---

## Architecture Overview

**Source → Lakehouse → Warehouse → Power BI**

### Data Flow

#### Bronze Layer
- Raw data ingestion from CSV (simulating an operational source system)
- Stored as Delta tables in Fabric Lakehouse

#### Silver Layer
- Data cleansing and type enforcement
- Timestamp standardization
- Business-ready schema preparation

#### Gold Layer
- Incremental MERGE (Upsert) logic using Delta Lake
- Idempotent design
- Business-consumable fact table

#### Warehouse Layer
- Gold data loaded into Fabric Warehouse
- Optimized for reporting and analytics
- Power BI–ready tables

---

## Key Concepts Demonstrated

- Delta Lake & ACID transactions
- Incremental processing with MERGE INTO
- Idempotent data pipelines
- Lakehouse → Warehouse integration
- Enterprise-ready data modeling
- Separation of concerns across layers

---

## Repository Structure

```text
fabric-end-to-end-data-engineering/
│
├── notebooks/
│   ├── bronze_ingestion.ipynb
│   ├── silver_transform.ipynb
│   ├── gold_merge.ipynb
│   └── warehouse_reporting.ipynb
│
├── pipelines/
│   └── .gitkeep
│
├── warehouse/
│   └── .gitkeep
│
├── powerbi/
│   ├── kpi_total_revenue.png
│   ├── kpi_total_quantity.png
│   ├── revenue_over_time.png
│   ├── revenue_by_product.png
│   └── sales_detail_table.png
│
├── diagrams/
│   └── .gitkeep
│
└── README.md

## Technologies Used

- Microsoft Fabric
- Lakehouse (Delta Tables)
- Fabric Warehouse
- PySpark
- Delta Lake
- Power BI (Direct Lake)

---

## Reporting & Analytics

The final Gold data is loaded into a Fabric Warehouse and is designed to be consumed directly by Power BI using Direct Lake for high-performance analytics and reporting.

---

## Incremental Data Processing

This project implements CDC-style incremental updates using:
- Business keys (SaleID)
- Delta Lake MERGE INTO
- Update & Insert logic to prevent duplicate records
The pipeline is safe to rerun multiple times without data duplication.

---

## Why This Project Matters

This project reflects how modern data engineering teams:
- Build scalable Lakehouse architectures
- Maintain clean separation between raw, refined, and analytical data
- Serve business intelligence teams with reliable, trusted datasets
It is designed to closely resemble real-world enterprise data engineering workflows.

---

## Future Enhancements

- Fabric Pipelines & Scheduling
- Automated incremental loads
- Power BI dashboards
- Data quality checks
- Monitoring & logging

---

## Visual Analytics (Fabric)

Visual analytics are demonstrated using Fabric-native notebook visualizations and Power BI–style charts. These visuals
represent how the Gold layer data is ultimately consumed by analytics and BI teams via Fabric Warehouse and Direct Lake.

---

## 👤 Author

Alex Elamin
Data Engineer | SQL | Microsoft Fabric | Power BI

🔗 GitHub: https://github.com/alex-elamin

🔗 LinkedIn: https://www.linkedin.com/in/alexelamin

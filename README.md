# End-to-End Sales Data Warehouse - ETL Pipeline 🚀

This project implements a complete ETL process to build a **Sales Data Warehouse**. It automates the extraction, transformation, and loading of sales data from source systems into a Star Schema architecture using **SSIS**.

## 🛠️ Tech Stack
* **ETL Tool:** SQL Server Integration Services (SSIS)
* **Database:** Microsoft SQL Server
* **Data Modeling:** Star Schema (FactSales & Dimensions)

## 📊 Pipeline Visuals

### 1. Control Flow (Orchestration)
The master workflow showing the sequence of loading dimensions and the final fact table.
![Control Flow](Screenshots/ETL_Control_Flow.png)

### 2. Data Flow Implementations
Detailed logic for each table within the pipeline:

| Table | Strategy | Data Flow Preview |
| :--- | :--- | :--- |
| **DimCustomer** | **SCD Type 2** (Historical Tracking) | ![Customer SCD](Screenshots/DimCustomer_SCD_DataFlow.png) |
| **DimProduct** | Full Dimension Load | ![Product Flow](Screenshots/DimProduct_DataFlow.png) |
| **DimSalesman** | Sales Personnel Mapping | ![Salesman Flow](Screenshots/DimSalesman_DataFlow.png) |
| **FactSales** | Core Transactional Loading | ![Fact Flow](Screenshots/FactSales_DataFlow.png) |

## ✅ Key Engineering Features
* **Slowly Changing Dimension (SCD Type 2):** Implemented for `DimCustomer` to maintain a history of customer data changes over time.
* **Lookup Transformations:** Used to validate and map business keys from dimensions into the fact table.
* **Data Integrity:** Ensuring all sales transactions are linked correctly to their respective products, customers, and salesmen.

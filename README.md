# End-to-End-Sales-DataWarehouse-ETL
A professional ETL pipeline using SSIS to migrate data from an OLTP source to a Star Schema Data Warehouse. Includes full implementation of SCD Type 2, fact table loading, and surrogate key management.
# End-to-End Sales Data Warehouse ETL Project (SSIS)

## 📌 Project Overview
This project showcases a complete **ETL (Extract, Transform, Load)** pipeline designed to migrate transactional data from an **OLTP Source** to a structured **Data Warehouse (Star Schema)**. The primary goal is to support business intelligence by maintaining historical data accuracy and optimizing query performance.

## 🛠️ Tech Stack
* **Database:** Microsoft SQL Server (T-SQL)
* **ETL Tool:** SQL Server Integration Services (SSIS)
* **Data Modeling:** Star Schema (Fact & Dimension Tables)

## 🏗️ Core Features & Implementation
### 1. Advanced Data Modeling
* **Star Schema Design:** Transformation of normalized source data into a high-performance Star Schema including `FactSales`, `DimCustomer`, `DimProduct`, and `DimDate`.
* **Surrogate Key Management:** Implementation of automated identity keys for all dimension tables.

### 2. Robust ETL Workflows (SSIS)
* **Slowly Changing Dimensions (SCD Type 2):** Implemented historical tracking for `DimCustomer`, ensuring that changes in customer attributes are preserved over time with `StartDate` and `EndDate` logic.
* **Complex Data Flows:** * Used **Lookup Transformations** to map business keys to surrogate keys.
    * Integrated **Derived Columns** for data cleaning and transformation.
    * Managed **Union All** operations to merge historical and new data streams.
* **Incremental Loading:** Designed logic to handle data updates efficiently without full table reloads.

### 3. Professional Standards
* **Naming Conventions:** Applied industry-standard prefixes (`SRC_`, `DST_`, `SQL_`, `DFT_`) for all components to ensure maintainability and clarity.
* **Optimization:** Configured OLE DB destinations for bulk loading to improve performance.

## 📁 Project Structure
* `SQL_Scripts/`: T-SQL scripts for schema creation (Source & Warehouse).
* `SSIS_Packages/`: The `.dtsx` files containing the ETL logic.
* `Documentation/`: Architecture diagrams and screenshots of the Control Flow and Data Flow.

## 🚀 Setup Instructions
1. **Prepare Databases:** Run the scripts in the `SQL_Scripts` folder to set up `Sales_OLTP` and `Sales_OLAP`.
2. **Configure SSIS:** Open the solution in Visual Studio and update the **Connection Managers** to point to your local SQL Server instance.
3. **Run Pipeline:** Execute the dimension packages first to populate the Star Schema, followed by the Fact loading package.

---
**Developed by:** [Your Name]
**Focus:** Data Engineering & Analytics

# Coffee Sales Analysis - Power BI Task

## Overview
This repository contains a Power BI project analyzing coffee shop sales data. The objective is to transform, clean, and model the data to generate meaningful insights.

## Task Breakdown

### 1. Import Data
- Load the provided Coffee Shop Sales dataset into Power BI.

### 2. Data Transformation
- Check for column names, data types, missing, and error values.
- Normalize the dataset by splitting it into separate tables:
  - **Transactions**: `transaction_id`, `transaction_date`, `transaction_time`, `transaction_qty`, `store_id`, `product_id`.
  - **Stores**: `store_id`, `store_location`.
  - **Products**: `product_id`, `unit_price`, `product_category`, `product_type`, `product_detail`.
- Remove duplicate entries from each table.

### 3. Data Modeling
- Identify **Fact** and **Dimension** tables.
- Establish relationships between the tables.
- Define the schema.

### 4. Power Query Analysis
#### 4.1 Create a Column for Sales
- Merge `unit_price` from **Products** into the **Transaction** table.
- Create a custom column:
  ```
  Sales = unit_price * transaction_qty
  ```

#### 4.2 Conditional Column
- Create a new column `Is High Quantity`:
  - If `transaction_qty > 4`, return **"Yes"**; otherwise, **"No"**.

#### 4.3 Parameters Calculation
- Compute and store the following parameters:
  - **Total Sales**: Sum of all sales.
  - **Average Transaction Quantity**: Average of `transaction_qty`.

#### 4.4 Filter Based on Parameters
- Duplicate the **Transactions** table.
- Filter transactions where `transaction_qty` is greater than **Average Transaction Quantity**.

#### 4.5 Sales Based on Location
- Merge `Sales` from **Transaction** into **Store**.
- Aggregate the sum of sales per store location.

#### 4.6 Count of Products in Each Category
- Duplicate the **Products** table.
- Apply `GroupBy` to count the number of products in each category.
- Rename the table to **Product Summary**.

## Evaluation Criteria
| Task | Marks |
|------|-------|
| Data Transformation | 8 |
| Data Modeling | 10 |
| Power Query Analysis | 12 |
| **Total** | **30** |

## Tools & Technologies Used
- **Microsoft Power BI** for data analysis and visualization
- **Power Query** for data transformation
- **DAX (Data Analysis Expressions)** for calculations and aggregations

## How to Use This Repository
1. Clone this repository:
   ```bash
   git clone https://github.com/osamanoor17/coffee-sales-analysis.git
   ```
2. Open the Power BI file and review the dataset transformations.
3. Explore the data model and relationships.
4. Analyze the insights generated using Power BI visuals.

## Author
- [LinkedIn Profile](https://www.linkedin.com/in/mosamanoor/)

## License
This project is open-source and available for educational and non-commercial use.

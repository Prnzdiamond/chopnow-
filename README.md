# ChopNow Food Delivery Analytics Project

This project contains the data, cleaning pipeline, and Power BI visualization assets for **ChopNow**, a food delivery platform operating across major urban centers in Nigeria (including Lagos, Abuja, Port Harcourt, Ibadan, and Enugu). 

The goal of this project is to analyze food delivery operations, customer behavior, restaurant performance, and rider efficiency across multiple years (2024–2026).

---

## 📂 Repository Structure & File Descriptions

This project is organized into raw data sources, cleaned and transformed datasets, annual transactional logs, and the final interactive Power BI business intelligence report.

### 1. Business Intelligence & Dashboards
* **`class 5 assignment.pbix`**
    * **Description:** The core Power BI Desktop file containing the interactive data model, DAX measures, and analytical dashboards.
    * **Key Visualizations:** Includes KPIs for total revenue, order fulfillment rates, delivery efficiency (minutes per order), restaurant performance rankings, and customer retention metrics.

### 2. Cleaned Datasets (`chopnow_clean.xlsx - *.csv`)
These files represent the clean, processed operational tables that serve as the single source of truth for reporting.
* **`chopnow_clean.xlsx - customers.csv`**
    * Contains standardized records of registered users, including unique `customer_id`, `customer_name`, geographic metadata (`city`, `area`), and their exact `signup_date`.
* **`chopnow_clean.xlsx - restaurants.csv`**
    * Lists active restaurant partners mapped to their respective `restaurant_id`, `restaurant_name`, standardized cuisine categories (`cuisine_name`), location, and overall `restaurant_rating`.
* **`chopnow_clean.xlsx - riders.csv`**
    * Details the logistics fleet, including `rider_id`, `rider_name`, localized operation `city`, and their logistical `vehicle_type` (e.g., Bike, Bicycle, Car).
* **`chopnow_clean.xlsx - orders.csv`**
    * The master consolidated transactional log containing order IDs, metrics like `food_amount`, `delivery_fee`, `total_amount`, user feedback ratings, and logistics flags (`delivery_speed`, `delivery_minutes`, `payment_method`).

### 3. Historical Annual Transactions
* **`orders_2024.csv`** | **`orders_2025.csv`** | **`orders_2026.csv`**
    * **Description:** Time-series partitions containing raw transactional order data for each respective calendar year. These files include individual item counts, food costs in Nigerian Naira (₦), delivery metrics, customer feedback ratings, and payment channels (Wallet, Card, Cash, Bank Transfer).

### 4. Raw Unprocessed Datasets (`chopnow_raw.xlsx - *.csv`)
These tables represent the legacy/dirty data ingested directly from operational databases before cleaning, deduplication, and case normalization.
* **`chopnow_raw.xlsx - customers.csv`**: Contains dirty strings, trailing spaces, unformatted names, and unstructured operational comments (`member_notes`).
* **`chopnow_raw.xlsx - restaurants.csv`**: Contains raw restaurant records with unstandardized city casing (e.g., `lagos`, `IBADAN`) and corporate reference codes (`ref_code`).
* **`chopnow_raw.xlsx - riders.csv`**: Contains raw fleet logs with system integration statuses (`sync_flag`).
* **`chopnow_raw.xlsx - cuisines.csv`**: The raw dimensional mapping table connecting `cuisine_id` directly to their respective food types.

---

## 🛠️ Data Insights & Metrics Covered

The project tracks several operational KPIs crucial for logistics and quick-service restaurant (QSR) management:
* **Sales Performance:** Gross Merchandise Value (GMV), net food revenue, and delivery fees broken down by city and area.
* **Logistics Efficiency:** Delivery turnaround time (`delivery_minutes`) analyzed across vehicle classes (Bikes vs. Cars vs. Bicycles) and assigned speeds.
* **Customer Experience:** Distribution of ratings across cuisine categories, payment types, and operational regions to pinpoint service bottlenecks.
* **Payment Analysis:** Preference trends between modern digital wallets, debit cards, bank transfers, and cash-on-delivery.

---

## 🚀 How to Use This Project

1.  **Replicate the Data Model:** Import the data from the annual `orders_*.csv` and dimension tables into SQL or Python for ETL exercises.
2.  **Explore the Dashboard:** Open `class 5 assignment.pbix` using **Power BI Desktop** to inspect the relationship mappings (Star Schema) and interact with the executive report.

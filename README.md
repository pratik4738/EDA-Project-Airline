# 🛫 Airlines Management – Data Curation, Wrangling, Cleansing & Predictive Analytics

<img width="2560" height="1707" alt="image" src="https://github.com/user-attachments/assets/7711726c-661a-43e0-99f8-b8446619b2dd" />

### 🧩 Domain: Aviation / Transportation Analytics  
### 📈 Difficulty: Very High  
### 🎯 Use Case: Clean and unify passenger, booking, and flight data for predictive modeling and operational insights.

---

## 🧠 Problem Statement

Our company operates a diverse fleet of aircraft ranging from small business jets to medium-sized machines, offering high-quality air transportation services.  
However, due to factors such as **stricter environmental regulations, rising fuel prices, higher taxes, and increased labor costs**, profitability is under pressure.  

Description : Our company operates a diverse fleet of aircraft ranging from small business jets to medium-sized machines. We have been providing high-quality air transportation services to our clients for several years, and our primary focus is to ensure a safe, comfortable, and convenient journey for our passengers. However, we are currently facing challenges due to several factors such as stricter environmental regulations, higher flight taxes, increased interest rates, rising fuel prices, and a tight labor market resulting in increased labor costs. As a result, the company's profitability is under pressure, and they are seeking ways to address this issue. To tackle this challenge, they are looking to conduct an analysis of their database to find ways to increase their occupancy rate, which can help boost the average profit earned per seat.Our company operates a diverse fleet of aircraft ranging from small business jets to medium-sized machines. We have been providing high-quality air transportation services to our clients for several years, and our primary focus is to ensure a safe, comfortable, and convenient journey for our passengers. However, we are currently facing challenges due to several factors such as stricter environmental regulations, higher flight taxes, increased interest rates, rising fuel prices, and a tight labor market resulting in increased labor costs. As a result, the company's profitability is under pressure, and they are seeking ways to address this issue. To tackle this challenge, they are looking to conduct an analysis of their database to find ways to increase their occupancy rate, which can help boost the average profit earned per seat.

---


## 🎯 Project Objectives

1. **Clean and standardize** data from multiple operational systems (flights, bookings, passengers).  
2. **Ensure data quality** through validation, cleansing, and schema alignment.  
3. **Unify datasets** into a consistent model for predictive and descriptive analytics.  
4. **Predict key outcomes:**
   - Flight delays
   - Passenger no-shows
   - Revenue optimization  
5. **Develop actionable insights** to improve flight occupancy and reduce operational inefficiencies.

---

## 🧩 Datasets Overview

**Data Sources:**
- `passengers.xlsx`
- `bookings.xlsx`
- `flights.xlsx`
- `aircraft.xlsx`
- `routes.xlsx`
- `employees.xlsx`

**Data Description:**
| Dataset | Description | Key Fields |
|----------|--------------|-------------|
| **Passengers** | Passenger profile and demographics | `passenger_id`, `gender`, `age`, `frequent_flyer` |
| **Bookings** | Ticketing and payment details | `booking_id`, `passenger_id`, `flight_id`, `fare_paid`, `booking_date` |
| **Flights** | Flight schedule and performance | `flight_id`, `aircraft_id`, `route_id`, `departure_time`, `arrival_time`, `delay_minutes` |
| **Aircraft** | Fleet details and specifications | `aircraft_id`, `type`, `capacity`, `status` |
| **Routes** | Origin-destination route information | `route_id`, `source_city`, `destination_city`, `distance_km` |
| **Employees** | Flight crew and staff information | `employee_id`, `assigned_flight`, `role`, `hours_worked` |

---

## 🧭 KPIs Defined

- ✈️ **Delay Rate:** % of delayed flights per route or aircraft type  
- 👥 **Occupancy Rate:** Seats occupied vs total seats  
- 💰 **Average Revenue per Flight:** Total revenue ÷ number of flights  
- 🔁 **Passenger Loyalty Index:** Number of repeated bookings per passenger  

---

## 🔧 Step-by-Step Workflow


### 🟦 1. Understand Business Context
- Predict factors influencing **flight delays, no-shows, and revenue**.  
- Define KPIs: *Delay Rate, Occupancy Rate, Average Revenue per Flight*.  
- Align project goals with **revenue optimization and customer behavior analysis**.


**Business Goal:**  
Improve flight profitability by analyzing factors affecting delays, no-shows, and revenue.

**KPIs:**
- Delay Rate = (Delayed Flights / Total Flights) × 100
- Occupancy Rate = (Seats Booked / Total Seats Available) × 100
- Average Revenue per Flight = Total Fare / Total Flights

**Stakeholders:**
- Revenue Team → maximize revenue per flight
- Operations Team → reduce delays
- Customer Experience Team → lower no-shows
- Data Science Team → create predictive models

**Analytical Focus:**
Predictive modeling + data wrangling for clean, unified analytics-ready datasets.


---

### 🟨 2. Data Discovery and Ingestion
- Datasets: `passengers`, `bookings`, `flights`, `aircraft`, `routes`, `employees`  
- Tools: `pandas.read_excel()`, `SQL import`  
- Record metadata: sheet names, row counts, timestamp ranges  
  Done --
---

### 🟩 3. Data Profiling
- Tools: `pandas-profiling`, `Sweetviz`, `describe()`  
- Detect nulls, duplicates, and outliers (e.g., unrealistic ticket prices, 0 kg baggage)  
- Validate data types and formats  

---

### 🟥 4. Schema Alignment & Standardization
- Normalize column names to `snake_case`  
- Standardize date formats (ISO 8601)  
- Recode categorical fields (gender, seat_class, checkin_status)  
- Clean inconsistent city and route names  

---

### 🟪 5. Data Cleaning
- Impute missing ticket prices by average per class  
- Drop duplicate bookings and retired aircraft  
- Fix incorrect booking dates (e.g., after departure)  
- Remove anomalies (e.g., baggage > 50 kg)  

---

### 🟫 6. Data Integration and Merging
- Join `bookings + passengers + flights`  
- Merge `flights` with `routes` and `aircraft`  
- Join `employees` via `assigned_flight`  
- Validate all foreign keys — ensure no orphan records  

---

### 🟦 7. Data Transformation
- Derive new features:
  - `flight_delay_flag`
  - `passenger_age`
  - `flight_revenue`
  - `booking_lead_time = departure_date - booking_date`  
- Aggregate metrics:
  - Flight occupancy rate  
  - Passenger loyalty index  
  - Employee flight hours  

---

### 🟨 8. Data Validation & Quality Checks
- Validate consistency of flight and passenger IDs  
- Flag any future-dated bookings  
- Write data tests using `pytest` or Pandas assertions  

---

### 🟩 9. Documentation
- Build a **Data Dictionary**  
- Include transformation logs, null statistics, and sample records  
- Annotate Jupyter cells for clarity  

---

### 🟥 10. Export & Delivery
- Export cleaned datasets (`.csv` or `.xlsx`)  
- Generate model-ready data  
- Include profiling report, validation logs, and final README  

---

## 🤖 Predictive Analytics Tasks

### 🔹 **Regression Task**
**Goal:** Predict total fare paid (`fare_paid`)  
- Models: Linear Regression, Ridge, Lasso  
- Features: `seat_class`, `baggage_kg`, `booking_lead_time`, `frequent_flyer`, `flight_duration`  
- Metrics: RMSE, MAE, R²  

---

### 🔹 **Association Rule Mining**
**Goal:** Identify passenger behavior patterns (no-shows, cancellations)  
- Technique: Apriori / FP-Growth  
- Example Rule:  
  > IF seat_class = Economy AND baggage_kg < 10 → higher chance of no-show  

---

### 🔹 **Decision Tree Classification**
**Goal:** Predict passenger **no-show probability** (`checkin_status = 'No Show'`)  
- Models: Decision Tree, Random Forest, Gradient Boost  
- Features: `passenger_age`, `seat_class`, `frequent_flyer`, `booking_lead_time`  
- Metrics: Accuracy, Recall, F1 Score, AUC  
- Outputs: Confusion matrix, ROC curve, feature importance  

---

## 🚧 Main Challenges

1. Inconsistent data formats and naming conventions across sheets.  
2. Missing or incorrect booking and flight timestamps.  
3. Redundant or orphaned records (e.g., missing route IDs).  
4. Data imbalance in delay/no-show classification.  
5. Large dataset size — requiring efficient memory handling.  

---

## 🧾 Deliverables

- ✅ Cleaned, validated master dataset  
- ✅ Exploratory and profiling reports  
- ✅ Predictive models with evaluation metrics  
- ✅ Visual dashboards for KPIs  
- ✅ Final documentation and README  

---

## 💻 Tech Stack

| Category | Tools / Libraries |
|-----------|------------------|
| Data Processing | Pandas, NumPy |
| Profiling | Pandas-Profiling, Sweetviz |
| Data Cleaning | Scikit-learn (SimpleImputer, KNNImputer) |
| Visualization | Matplotlib, Seaborn, Plotly |
| ML Modeling | Scikit-learn, XGBoost |
| Documentation | Jupyter, Markdown, Notion |

---

By pratik Patil and its team 
---


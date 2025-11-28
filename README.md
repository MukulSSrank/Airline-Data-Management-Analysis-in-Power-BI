# Airline Data Management & Analysis in Power BI

This project is an end-to-end **Airline Data Management and Analysis** solution built in **Power BI**.  
It focuses on understanding **flight operations, passenger distribution, and ticket booking status** using an interactive dashboard, DAX measures, and Power Query transformations. 

> ✅ Good for **Data Analyst / BI Analyst / Power BI Developer** roles  
> ✅ Uses ATS-friendly keywords: *Power BI, Power Query, DAX, data modeling, row-level security (RLS), dashboarding, KPI reporting, flight analytics*.

---

## 📂 Dataset Overview

Three core datasets were used:

- **Flight_Information**
  - Fields: `FlightID`, `FlightNumber`, `Airline`, `Destination`, `FlightStatus`, etc.
  - Used to analyze **airline performance**, **destinations**, and **flight status**.

- **Passenger_Information**
  - Fields: `PassengerID`, `FlightID`, `SeatNumber`, etc.
  - Used to calculate **passenger counts per flight and airline**.

- **Ticket_Information**
  - Fields: `TicketID`, `FlightID`, `BookingStatus` (Confirmed, Cancelled, Pending), etc.
  - Used to understand **ticket booking trends and status distribution**.

All three tables are related using **`FlightID` as the key**, forming a **star-schema style model** in Power BI.

---

## 🛠 Tech Stack & Skills

- **Tool:** Microsoft Power BI Desktop + Power BI Service
- **Technologies / Features:**
  - Power Query (data cleaning & transformation)
  - Data Modeling & Relationships
  - DAX Measures & Calculated Tables
  - Interactive Visualizations (bar chart, pie chart, matrix)
  - Row-Level Security (RLS)
  - Scheduled Data Refresh

- **Skills Demonstrated (ATS keywords):**
  - Data Cleaning, Data Transformation
  - Data Modeling & Relationship Design
  - Aggregation & KPI Calculation with DAX
  - Dashboard Design & Storytelling
  - Row-Level Security (RLS) Configuration
  - Publishing & Refresh in Power BI Service

---

## 🔧 Task Breakdown

### 1️⃣ Data Preparation & Cleaning (Power Query)

- Imported the three datasets into **Power Query**.
- **Removed duplicates** and unnecessary columns (e.g., columns containing only null values).
- Cleaned and standardized columns:
  - Ensured consistent data types for keys like `FlightID`.
  - Prepared `FlightStatus` and `BookingStatus` for analysis and conditional logic. :contentReference[oaicite:1]{index=1}  

**Result:** A **clean, analysis-ready model** that can be refreshed and reused.

---

### 2️⃣ Data Modeling

- Created relationships between:
  - `Flight_Information` (primary table)
  - `Passenger_Information` (Many-to-One via `FlightID`)
  - `Ticket_Information` (Many-to-One via `FlightID`)
- Configured relationship cardinality & cross-filtering direction correctly in **Model View**. :contentReference[oaicite:2]{index=2}  

**Impact:** This allowed accurate passenger counts, ticket counts, and flight-level aggregation across all tables.

---

### 3️⃣ Enhanced Data Insights (Power Query Transformations)

In **Power Query**, additional logic was added to enrich the dataset: :contentReference[oaicite:3]{index=3}  

- **Conditional Column – Flight Status Category**
  - Classified each flight as **"Best"** or **"To Be Improved"** based on the `FlightStatus` field.
- **Extracted Flight Number**
  - Used **Column From Examples** to extract the numeric **flight number** from the `FlightNumber` string.

These transformations made it easier to filter and analyze flights by quality and ID.

---

### 4️⃣ DAX Calculations

Key measures and tables created using **DAX**: :contentReference[oaicite:4]{index=4}  

- **Total Passengers**
  ```DAX
  Total_Passengers = COUNT(Passenger_Information[PassengerID])

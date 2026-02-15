
# ♻️ MRF Digital Suite – Operational Analytics & Reporting Platform
![Status](https://img.shields.io/badge/Status-Active-success)
![Python](https://img.shields.io/badge/Python-3.10+-blue)
![Streamlit](https://img.shields.io/badge/Streamlit-1.31+-ff4b4b)

## 📌 Overview

**MRF Digital Suite** is an end-to-end operational analytics system designed to ingest, validate, analyze, and report municipal waste-load data from Material Recovery Facilities (MRFs).

The system processes structured CSV data, stores it in a relational database, computes key operational metrics, and generates automated analytical reports (CSV & PDF) along with an interactive dashboard for real-time insights.

This project demonstrates practical data engineering, analytics, and automation workflows in a real-world operations setting.

---

## 🎯 Key Features

### 🔹 Data Ingestion & Validation

* CSV import with schema normalization
* Append or overwrite import mode
* Validation for missing/invalid fields
* Duplicate record detection
* Error handling with skipped row tracking

### 🔹 Database Layer

* SQLite relational database
* Structured schema for waste_records
* Parameterized queries for safe data insertion
* Modular data access functions

### 🔹 KPI & Analytics Engine

Computes operational metrics including:

* Total waste processed
* Revenue potential (material-based pricing model)
* Weekly waste trends
* Material distribution breakdown
* Destination analysis
* Average daily waste
* Today’s operational summary

Revenue is dynamically calculated using configurable material rate mappings.

---

### 🔹 Automated Reporting

* CSV export for raw data reporting
* Styled PDF report generation using ReportLab
* Summary statistics tables
* Material-wise revenue breakdown
* Destination percentage analysis
* Time-range filtering support
* Dynamic report timestamps

---

### 🔹 Interactive Dashboard (Streamlit + Plotly)

* KPI metric cards
* Weekly trend visualization
* Material composition pie chart
* Revenue by material bar chart
* Destination breakdown
* Real-time dashboard refresh
* Downloadable data exports

---

## 🏗 System Architecture

```
CSV Upload → Validation & Cleaning → SQLite DB → Aggregation Logic → 
KPI Engine → Dashboard API → Streamlit UI
                           ↓
                     CSV & PDF Reports
```

---

## 🛠 Tech Stack

* Python
* SQLite
* Pandas
* Streamlit
* Plotly
* ReportLab
* SQL (aggregation queries, filtering, grouping)
* Standard Python libraries (datetime, csv, os, uuid)

---

## 🗂 Project Structure

```
MRFDigital-Suite/
│
├── app.py                 # Streamlit frontend & routing logic
├── dashboard.py           # Aggregation & KPI computation
├── report_generator.py    # Data import, validation & PDF/CSV reporting
├── mrf_data.db            # SQLite database file
├── uploads/               # Uploaded CSV files
├── reports/               # Generated reports
├── templates/             # HTML templates (if applicable)
├── static/                # Static assets
└── README.md
```

---

## 📊 Example KPIs Generated

* Total Waste Processed (kg)
* Revenue Potential (₹)
* Average Daily Waste
* Weekly Waste Trend (Last 30 Days)
* Top Material Category
* Main Destination
* Revenue by Material Type

---

## 🚀 How to Run the Project

### 1️⃣ Install Dependencies

```bash
pip install streamlit pandas plotly reportlab
```

### 2️⃣ Run Application

```bash
streamlit run app.py
```

### 3️⃣ Use the Dashboard

* Load sample data (100 synthetic records)
* Upload custom CSV data
* Generate reports
* Download exports

---

## 📥 CSV Import Format

Expected fields:

```
date, vehicle_id, weight, material, destination
```

Alternate header variations are supported and normalized automatically.

---

## 📄 Report Output

Generated reports include:

* Total waste processed
* Number of loads
* Average load weight
* Top material & destination
* Material-wise revenue table
* Destination percentage distribution
* Time-stamped generation details

Reports are saved in the `/reports` directory.

---

## 🔐 Data Integrity Features

* Duplicate detection before insert
* Validation for invalid weight values
* Missing essential field checks
* Optional append mode for safe incremental imports

---

## 🧠 What This Project Demonstrates

* End-to-end data pipeline thinking
* Structured relational data modeling
* SQL-style aggregation logic
* KPI computation aligned to business needs
* Data validation & integrity controls
* Automation of reporting workflows
* Interactive analytics visualization
* Clean modular code organization

---

## 📌 Future Improvements

* Migration to PostgreSQL for production-scale deployment
* Role-based access control
* Logging system for import & report tracking
* Scheduled automated report generation
* REST API deployment option

---

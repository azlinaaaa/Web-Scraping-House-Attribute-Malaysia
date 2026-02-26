# 🏠 Malaysia Residential Property Intelligence System

### Automated Web Scraping & Structured Market Dataset (Putrajaya & Sabah)

---

## 📌 Project Overview

This project develops an automated web scraping pipeline to extract residential property listings from **iProperty Malaysia** for:

* 🏙️ Putrajaya
* 🌴 Sabah

The system transforms dynamically rendered real estate listings into structured, analytics-ready datasets suitable for:

* Market analysis
* Business intelligence dashboards
* Housing price modeling
* Regional comparison studies
* Investment insights

This project demonstrates real-world data acquisition, automation, and data engineering fundamentals.

---

## 🎯 Project Objectives

### Primary Objective

Build an automated system capable of extracting complete residential listings from a dynamic JavaScript-based website.

### Secondary Objectives

* Handle infinite scrolling content
* Automate multi-page navigation
* Extract structured housing attributes
* Maintain row-level data consistency
* Export clean CSV datasets
* Prepare foundation for analytics & ML modeling

---

## 🛠️ Tech Stack

* **Python**
* **Selenium**
* **ChromeDriver (WebDriver Manager)**
* **XPath**
* **CSV**
* **Explicit Wait Handling**

---

## 🏗️ System Architecture

```
iProperty Website
        ↓
Selenium Browser Automation
        ↓
Dynamic Content Rendering
        ↓
Auto Scroll Detection
        ↓
XPath Data Extraction
        ↓
Pagination Loop
        ↓
Structured Dataset Export (CSV)
        ↓
Analytics / BI / ML Integration
```

---

## ⚙️ Technical Implementation

### 1️⃣ Browser Automation

* Custom User-Agent to simulate real browser traffic
* GPU disabled for stability
* ChromeDriver auto-managed via WebDriver Manager

---

### 2️⃣ Dynamic Content Handling

The website loads listings using JavaScript.
To ensure full rendering:

```python
WebDriverWait(driver, 10).until(
    EC.presence_of_element_located(...)
)
```

This prevents partial or incomplete data extraction.

---

### 3️⃣ Infinite Scroll Strategy

The scraper:

1. Captures current page height
2. Scrolls to bottom
3. Waits for additional listings
4. Compares page height
5. Stops when no further content loads

Ensures all listings on a page are captured.

---

### 4️⃣ Multi-Page Pagination

The system:

* Detects “Next Page” button
* Clicks automatically
* Continues scraping until last page
* Stops gracefully when pagination ends

---

### 5️⃣ Null-Safe Data Extraction

Each attribute uses conditional extraction:

```python
element = listing.find_elements(...)
value = element[0].text.strip() if element else "N/A"
```

This ensures:

* No missing rows
* Dataset consistency
* Robust extraction

---

## 📂 Dataset Structure

Each row represents one residential property listing.

| Column         | Description           |
| -------------- | --------------------- |
| House Name     | Property title        |
| Price          | Listing price         |
| Location       | Property area         |
| Price per SqFt | Unit price            |
| Description    | Short listing summary |
| Bedroom        | Number of bedrooms    |
| Bathroom       | Number of bathrooms   |
| Carpark        | Parking spaces        |
| Agent Name     | Listing agent         |
| Post Date      | Date posted           |

---

## 📊 Dataset Output

Generated files:

* `iproperty_dataset_putrajaya.csv`
* `iproperty_dataset_sabah.csv`

---

## 🖼️ Dataset Preview

Create an `images/` folder in your repository:

```
project-folder/
│
├── README.md
├── iproperty_dataset_putrajaya.csv
├── iproperty_dataset_sabah.csv
└── images/
    ├── putrajaya_preview.png
    ├── sabah_preview.png
```


## 📊 Putrajaya Dataset Preview
![Putrajaya Dataset Preview](https://raw.githubusercontent.com/azlinaaaa/Web-Scraping-House-Attribute-Malaysia/main/Dataset-Preview/Putrajaya.png)

## 📊 Sabah Dataset Preview
![Sabah Dataset Preview](https://raw.githubusercontent.com/azlinaaaa/Web-Scraping-House-Attribute-Malaysia/main/Dataset-Preview/Sabah.png)

## 🔎 Data Quality Considerations

### Observed Challenges

* Price values in text format (e.g., RM 1.2mil)
* Missing carpark values
* Inconsistent formatting
* Mixed capitalization

### Required Post-Processing

* Remove currency symbols
* Convert million format to numeric
* Handle null values
* Standardize location names
* Feature engineering (e.g., price per bedroom)

---

## 📈 Analytical Opportunities

This dataset enables:

### 🏷 Market Segmentation

* Low / Medium / High price grouping
* Bedroom-based segmentation

### 📊 Regional Comparison

* Putrajaya vs Sabah median price
* Price per sqft analysis

### 📉 Distribution Analysis

* Price histogram
* Bedroom vs price correlation

### 🧠 Machine Learning Applications

* Regression (house price prediction)
* Classification (property segment)
* Clustering (market grouping)

---

## 🚀 Scalability & Future Enhancements

Possible upgrades:

* Automated monthly scraping
* Historical price tracking
* Database integration (MySQL/PostgreSQL)
* Cloud deployment
* Rental market extension
* Integration with Power BI dashboard
* Housing price prediction model

---

## 💼 Business Value

This project demonstrates capability in:

✔ Automated data pipeline development
✔ Dynamic website data extraction
✔ Structured dataset engineering
✔ Preparing raw web data for analytics
✔ Real-world market intelligence workflow

From a business perspective, this supports:

* Investment analysis
* Housing affordability studies
* Regional price comparison
* Data-driven property insights

---

## 🏆 Technical Competencies Demonstrated

* Web automation
* Data engineering fundamentals
* Dynamic content handling
* Fault-tolerant scraping
* Structured dataset design
* Analytics readiness

---

## 🔥 Why This Project Is Portfolio-Strong

Unlike static Kaggle analysis, this project:

* Builds dataset from scratch
* Handles real-world dynamic systems
* Demonstrates ownership of data acquisition
* Simulates industry-level data pipeline

It reflects end-to-end thinking:
**Raw Web Data → Structured Dataset → Business Insight**

---

## 📌 Disclaimer

This project was developed for educational and research purposes.
Website structure may change over time, requiring XPath updates.

---

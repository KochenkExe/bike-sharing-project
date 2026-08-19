# Bike Sharing Data Analysis & Dashboard

[![Streamlit App](https://static.streamlit.io/badges/streamlit_badge_black_white.svg)](https://dicoding-bike-sharing-sgswsm3j6l5khk4bacdwxn.streamlit.app/)
[![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An end-to-end data analytics and interactive dashboard project exploring usage patterns, seasonal influences, daily habits, and weather impacts in a bike-sharing system.

---

## Live Demo

You can access the live interactive Streamlit dashboard at:
[Bike Sharing Dashboard on Streamlit Cloud](https://dicoding-bike-sharing-sgswsm3j6l5khk4bacdwxn.streamlit.app/)

---

## Table of Contents

- [Project Overview](#project-overview)
- [Business Questions](#business-questions)
- [Key Insights & Findings](#key-insights--findings)
- [Dataset Information](#dataset-information)
- [Project Directory Structure](#project-directory-structure)
- [Installation & Setup](#installation--setup)
- [Running the Application](#running-the-application)
- [Dashboard Preview](#dashboard-preview)
- [Author & Credits](#author--credits)

---

## Project Overview

Bike-sharing rental processes are highly correlated with environmental and seasonal settings. For example, weather conditions, precipitation, day of the week, season, and hour of the day can heavily affect rental behavior.

This project delivers:
1. **Data Wrangling & Cleaning**: Assessing missing values, duplicate removal, and data type conversions.
2. **Exploratory Data Analysis (EDA)**: Uncovering hidden patterns and distributions across different seasons and weekdays.
3. **Interactive Visualization Dashboard**: Built using [Streamlit](https://streamlit.io/) to enable users and decision-makers to filter and visualize rental trends dynamically.

---

## Business Questions

This data analysis focuses on addressing the following core questions:

1. **Seasonality Impact**: *Di musim berapakah pengguna sepeda paling banyak?* (Which season experiences the highest number of bike rentals?)
2. **Daily Usage Trends**: *Berapa rata-rata pengguna sepeda per harinya dalam seminggu?* (What is the average daily usage across different days of the week?)
3. **Weather Condition Filter**: *Bagaimana pengaruh kondisi cuaca (cerah, mendung, hujan ringan) terhadap rata-rata pengguna per hari?* (How do specific weather conditions affect daily rental patterns?)

---

## Key Insights & Findings

* **Musim dengan Pengguna Terbanyak**:
  * **Musim Gugur (Fall)** mencatatkan jumlah peminjaman sepeda tertinggi dibandingkan musim lainnya.
  * Musim Semi (Spring) mencatatkan tingkat penggunaan paling rendah.
* **Tren Pengguna Harian**:
  * Rata-rata pengguna tertinggi terjadi pada hari **Jumat (Friday)** (~4,690 pengguna/hari) dan **Kamis (Thursday)** (~4,667 pengguna/hari).
  * Hari **Minggu (Sunday)** memiliki rata-rata pengguna paling rendah (~4,229 pengguna/hari).
* **Pengaruh Cuaca**:
  * Cuaca **Cerah (Clear / Few clouds)** memberikan kontribusi terbesar terhadap tingginya aktivitas peminjaman sepeda.
  * Cuaca buruk seperti **Hujan Ringan / Bersalju** menurunkan minat penggunaan secara signifikan.

---

## Dataset Information

The project utilizes the **Bike Sharing Dataset**, aggregated on both daily and hourly levels:

| File | Description | Records |
| :--- | :--- | :--- |
| `data/day.csv` | Aggregated bike sharing count per day (with weather and seasonal indicators) | 731 rows |
| `data/hour.csv` | Aggregated bike sharing count per hour | 17,379 rows |

### Feature Summary
* `dteday`: Date of rental records
* `season`: Season (`1`: Spring, `2`: Summer, `3`: Fall, `4`: Winter)
* `yr`: Year (`0`: 2011, `1`: 2012)
* `mnth`: Month (1 to 12)
* `holiday`: Whether the day is a holiday (`1`) or not (`0`)
* `weekday`: Day of the week (`0`: Sunday to `6`: Saturday)
* `workingday`: If day is neither weekend nor holiday (`1`), otherwise (`0`)
* `weathersit`:
  * `1`: Clear, Few clouds, Partly cloudy
  * `2`: Mist + Cloudy, Mist + Broken clouds
  * `3`: Light Snow, Light Rain + Thunderstorm
  * `4`: Heavy Rain + Ice Pellets + Thunderstorm
* `temp`: Normalized temperature in Celsius
* `atemp`: Normalized feeling temperature in Celsius
* `hum`: Normalized humidity
* `windspeed`: Normalized wind speed
* `casual`: Count of casual users
* `registered`: Count of registered users
* `cnt`: Total rental count (`casual` + `registered`)

---

## Project Directory Structure

```text
bike-sharing-project/
│
├── .devcontainer/                  # Visual Studio Code Remote Container configuration
│   └── devcontainer.json
│
├── dashboard/                      # Dashboard application files
│   ├── dashboard.py                # Streamlit dashboard implementation
│   ├── day.csv                     # Daily dataset copy for standalone dashboard deployment
│   └── hour.csv                    # Hourly dataset copy for standalone dashboard deployment
│
├── data/                           # Data storage folder
│   ├── day.csv                     # Main daily bike sharing data
│   └── hour.csv                    # Main hourly bike sharing data
│
├── screenshots/                    # Screenshots of the Streamlit dashboard
│   ├── Cuplikan layar_20-12-2024_7417_localhost.jpeg
│   ├── Cuplikan layar_20-12-2024_74121_localhost.jpeg
│   └── Cuplikan layar_20-12-2024_74145_localhost.jpeg
│
├── Proyek_Analisis_Data.ipynb      # Jupyter Notebook containing full EDA & visualizations
├── requirements.txt                # List of Python dependencies
├── url.txt                         # Streamlit Cloud deployment link
└── README.md                       # Documentation and project guide
```

---

## Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/KochenkExe/bike-sharing-project.git
cd bike-sharing-project
```

### 2. Create and Activate Virtual Environment (Recommended)

* **On Windows (PowerShell / Command Prompt):**
  ```powershell
  python -m venv venv
  .\venv\Scripts\activate
  ```

* **On macOS / Linux:**
  ```bash
  python3 -m venv venv
  source venv/bin/activate
  ```

### 3. Install Required Dependencies
```bash
pip install -r requirements.txt
```

---

## Running the Application

### A. Run Streamlit Dashboard
Execute the following command in your terminal from the project root:
```bash
streamlit run dashboard/dashboard.py
```
Or using Python module execution:
```bash
python -m streamlit run dashboard/dashboard.py
```
The dashboard will open automatically in your browser at `http://localhost:8501`.

### B. Explore with Jupyter Notebook
To run and inspect the step-by-step exploratory analysis:
```bash
jupyter notebook Proyek_Analisis_Data.ipynb
```
*(Or open directly in VS Code / Google Colab).*

---

## Dashboard Preview

The Streamlit dashboard presents interactive charts including:
- **Jumlah Pengguna per Musim**: Bar chart illustrating seasonal distribution.
- **Rata-rata Pengguna per Hari**: Bar chart comparing daily rental averages ordered from Monday through Sunday.
- **Filter Kondisi Cuaca**: Interactive dropdown allowing dynamic visualization based on selected weather types.

### 1. Overview & Weather Filter: Clear (Cerah)
![Dashboard Overview - Clear Weather](screenshots/Cuplikan%20layar_20-12-2024_74121_localhost.jpeg)

### 2. Weather Filter: Cloudy / Mist (Mendung)
![Dashboard - Cloudy Weather](screenshots/Cuplikan%20layar_20-12-2024_7417_localhost.jpeg)

### 3. Weather Filter: Light Rain / Snow (Hujan Ringan)
![Dashboard - Light Rain Weather](screenshots/Cuplikan%20layar_20-12-2024_74145_localhost.jpeg)

---

## Author & Credits

- **Name**: Harun Jeynaro Dewantoro Putra
- **Email**: [dewan9987@gmail.com](mailto:dewan9987@gmail.com)
- **Dicoding ID**: [hjeynaro](https://www.dicoding.com/users/hjeynaro)

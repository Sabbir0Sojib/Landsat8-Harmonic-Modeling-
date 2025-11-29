# Landsat 8 Harmonic Modeling with Google Earth Engine

This repository contains Google Earth Engine (GEE) scripts for analyzing **NDVI seasonality using Landsat 8** data.  
The model applies **harmonic regression** to detect vegetation trends and periodicity over time.

---

##  Project Overview
-  Uses **Landsat 8 TOA Reflectance Data** (`LANDSAT/LC08/C02/T1_TOA`).
-  Computes **NDVI (Normalized Difference Vegetation Index)**.
- Applies **harmonic regression** to capture seasonal variations.
- Visualizes **NDVI seasonality trends**.
- Exports results to **Google Drive** as GeoTIFF.

---

##  NDVI Seasonality Visualization
The image below represents **NDVI seasonality trends** computed using harmonic regression in GEE:

![NDVI Seasonality](https://github.com/Sabbirislam820/Landsat8-Harmonic-Modeling-/blob/main/Screenshot%202025-03-16%20052002.png?raw=true)

---

##  Methodology

### **1️ Load Landsat 8 Data**
The script filters **Landsat 8 Collection 2 TOA** images from **2015 to 2020**.

### **2 Apply Cloud Masking**
A **simple cloud score algorithm** removes cloud-contaminated pixels.

### **3️ Compute NDVI**
NDVI is calculated using the formula:

\[
NDVI = \frac{NIR - RED}{NIR + RED}
\]

Where:
- **NIR (Near Infrared)** = Band 5
- **RED** = Band 4

### **4️ Apply Harmonic Regression**
A **Fourier series-based harmonic model** captures periodic patterns in NDVI:

\[
NDVI = a_0 + a_1 \cos(t) + b_1 \sin(t)
\]

Where:
- **t** = Time in years (converted to radians)
- **a₀, a₁, b₁** = Regression coefficients

### **5️ Export Results to Google Drive**
- **Harmonic Trend Coefficients** → **GeoTIFF**
- **NDVI Seasonality Visualization** → **PNG**

---

##  File Structure

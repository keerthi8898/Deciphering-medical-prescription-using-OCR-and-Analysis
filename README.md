# Deciphering Medical Prescription using OCR and Analysis

## Project Overview
This project focuses on extracting, cleaning, and analyzing medical prescriptions using Optical Character Recognition (OCR) techniques. The goal is to transform scanned prescription images into structured data and derive meaningful insights through data analysis and visualization.

## Steps Followed

### 1. Data Collection
- Collected **100 printed prescriptions** that had a similar format.
- Ensured the prescriptions contained critical medical details like patient name, doctor name, department, dosage, and instructions.

### 2. OCR Processing
- Used **Tesseract OCR** to extract text from scanned images.
- Preprocessed images for better OCR accuracy:
  - **Grayscale Conversion**: Improved text clarity.
  - **Noise Reduction**: Applied Gaussian blur to remove background noise.
  - **Thresholding**: Used adaptive thresholding to enhance contrast.
  - **Morphological Transformations**: Used dilation and erosion to refine text regions.
- Converted extracted text into structured tabular data and saved it as a **CSV file**.

### 3. Implementation in Python
- **Libraries Used**:
  - `cv2`, `pytesseract`, `numpy`, `pandas`, `matplotlib`, `PIL`, `os`
  - Integrated with **Google Colab** for dataset handling via Google Drive.
- **Steps in Code Execution**:
  1. Mounted Google Drive to access dataset.
  2. Configured **Tesseract OCR** for text extraction.
  3. Implemented an **image preprocessing function**:
     - Converted images to grayscale.
     - Applied Gaussian blur and adaptive thresholding.
  4. Extracted text from images using **Tesseract OCR**.
  5. Structured extracted text into relevant fields like **Patient Name, Doctor Name, Age, Prescription, Dosage, Instructions**.
  6. Processed the first **10 prescription images** and visualized extracted text alongside images.
  7. Converted the extracted data into a **CSV file** and downloaded it for further processing.

### 4. Data Cleaning and ETL
- Loaded the extracted dataset into **Pandas** for processing.
- Handled missing values using **data imputation techniques**:
  
  #### Categorical Data (e.g., Name, Doctor Name, Gender, Department, Prescription, Instructions, Dosage)
  - **Mode Imputation**: Filled missing values with the most frequently occurring value.
  - **Forward/Backward Fill**: Used adjacent data to maintain logical continuity.
  - **Random Sampling**: Filled gaps with random values from the existing dataset.
  
  #### Numerical Data (e.g., Age, Payment Amount)
  - **Median Imputation**: Used the median to replace missing values for a balanced approach.
  - **Payment Estimate**: Averaged payment amounts within departments to estimate missing values.
  
  #### Text Data (e.g., Discharge Summary, Prescription, Instructions, Dosage)
  - **Contextual Guessing**: Assigned values based on similar department trends.
  - **Copy-Paste with Logic**: Used department-based standard prescriptions.
  - **Dosage & Instructions**: Maintained consistency with other similar cases.
  
  #### Conditional Logic (Using Common Sense)
  - **Gender from Name**: Derived gender based on common name conventions.
  - **Department-based Prescription**: Assigned standard medications based on the department.
  - **Payment Guesswork**: Estimated costs based on similar patient data.

### 5. Data Analysis & Visualization
- Cleaned and structured data was loaded into **Power BI** to create an interactive dashboard.
- Dashboard included:
  - **Patient Demographics Overview**
  - **Gender wise categorization per Department**
  - **Department wise Distribution**
  - **Payments and Estimates**
  
## Key Takeaways
- Successfully converted unstructured prescription images into structured, analyzable data.
- Implemented **OCR techniques in Python** for efficient text extraction.
- Employed **smart data imputation techniques** without using complex machine learning models.
- Created an insightful **Power BI dashboard** to present key findings.

This project showcases the power of **OCR, Python-based data preprocessing, and Power BI visualization** combined with **good data sense** to fill gaps and build a reliable dataset for medical analysis!

---
### How to Run This Project
1. Clone the repository.
2. Upload the prescription images of your own to Google Drive.
3. Open `Google Colab` and run the Python script.
4. Extracted text will be saved as a CSV file for further analysis.
5. Load the CSV into **Power BI** for dashboard creation.

### Dependencies
Ensure the following Python libraries are installed:
```bash
pip install opencv-python pytesseract numpy pandas matplotlib pillow
```



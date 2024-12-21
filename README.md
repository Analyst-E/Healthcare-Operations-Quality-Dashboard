# Background and Overview

As a Data Analyst at Starlight General Hospital, I collaborated with the management and clinical teams to design a comprehensive dashboard aimed at enhancing decision-making across key areas of hospital operations. Starlight General Hospital is a 500-bed facility dedicated to delivering high-quality healthcare services while ensuring operational efficiency and staff optimization. This dashboard was developed to provide a data-driven approach to monitoring and improving patient care, safety, and staff performance.

## The primary goals of this project were to:
- Analyze and visualize patient management metrics to monitor admissions, readmission rates, and demographic trends.
- Evaluate the quality and safety of healthcare delivery through key performance indicators such as incident reporting, infection rates, and patient satisfaction.
- Assess staff performance and utilization to understand productivity and its impact on patient outcomes.

The dashboard is structured into three interconnected pages, each addressing a specific aspect of hospital operations:
- **Patient Management Overview**: Provides insights into patient inflow, demographics, and the efficiency of bed occupancy and admissions.
- **Healthcare Quality Metrics**: Tracks healthcare delivery quality by monitoring incidents, protocol adherence, and patient satisfaction scores.
- **Staff Performance and Utilization**: Evaluates staff productivity, absenteeism, and the relationship between staffing levels and patient outcomes.

By utilizing this dashboard, Starlight General Hospital stakeholders can make informed decisions to optimize resources, improve patient outcomes, and ensure the highest standards of care.

# Data Structure Overview

## Entity Relationship Diagram (ERD)

![Db Diagram](https://github.com/user-attachments/assets/d0798b00-c6d3-4f6c-a9c0-bb2a362929b6)

The Entity Relationship Diagram (ERD) for this project illustrates the connections between the key data tables: Bed_Occupancy, Patients_Data, Admissions_Data, Satisfaction_Data, Safety_And_Compliance, Staff_Data, and Utilization_Data. These relationships highlight how patient information, staff performance, and operational metrics integrate to provide a comprehensive view of hospital performance.

### Data Domain and Key Data Points

The dataset covers the domain of healthcare operations and quality management, focusing on patient admissions, hospital resource utilization, staff performance, and compliance with safety standards. This structured dataset supports analysis across multiple dimensions, including:

- **Time Elements**: Admission and discharge dates, visit dates, and incident occurrence dates.
- **Patient Demographics**: Age, gender, and insurance type, enabling demographic analyses.
- **Operational Metrics**: Bed occupancy, length of stay, and readmissions.
- **Satisfaction and Compliance Metrics**: Patient feedback, satisfaction scores, and adherence to safety protocols.

These data points are universally applicable and provide a strong foundation for deriving actionable insights into healthcare management.

## Table Descriptions and Relationships
**Bed_Occupancy**: Captures daily bed utilization across hospital departments, providing insights into resource allocation and occupancy trends.
- Key Fields: Date, Department, Total Beds, Occupied Beds, Vacant Beds, Inpatient Admissions.

**Patients_Data**: Maintains demographic and admission details for all patients.
- Key Fields: Patient_ID (Primary Key), Name, Gender, Age, Insurance_Type, Admission Date, Discharge Date, Department.
- Linked to Admissions_Data and Satisfaction_Data.

**Admissions_Data**: Tracks patient admissions, including attending doctors and readmission status.
- Key Fields: Admission_ID (Primary Key), Patient_ID (Foreign Key), Doctor_ID (Foreign Key), Length_of_Stay, Readmission, Admission_type.
- Links to Patients_Data and provides detailed admission analysis.

**Satisfaction_Data**: Stores patient satisfaction scores and feedback to measure care quality.
- Key Fields: Patient_ID (Primary Key, Foreign Key), Visit_Date, Department, Satisfaction_Score, Feedback_Comments.
- Connected to Patients_Data.

**Safety_And_Compliance**: Monitors safety incidents, error types, and compliance rates.
- Key Fields: Incident_ID (Primary Key), Patient_ID (Foreign Key), Incident_Type, Error_Type, Hand_Hygiene_Compliance, Protocol_Adherence_Rate.
- Related to Patients_Data.

**Staff_Data**: Contains details about staff roles, attendance, and work hours.
- Key Fields: Staff_ID (Primary Key), Name, Role, Department, Overtime_Hours, Total_Days_Absent, Total_Workdays_since_Hire, Total Days Worked, Expected Work Hours, Actual Work Hours.

**Utilization_Data**: Tracks staff utilization metrics to assess efficiency.
- Key Fields: Staff_ID (Primary Key, Foreign Key), Overtime_Hours, Total_Days_Absent, Total_Workdays_since_Hire, Total_Days_Worked, Expected_Work_Hours, Actual_Work_Hours.
- Connected to Staff_Data.

# Insights Deep Dive

## **PATIENT MANAGEMENT AND OVERVIEW**

### **1. Admission Volume and Trends**
- **Total Admissions**: Increased to **982** in 2024 from **841** in 2023, representing a **14.4% growth**.
- **Peak Admission Months**:
  - 2024: March saw a peak with **135 admissions**.
  - 2023: November peaked at **98 admissions**.
- **Monthly Volume Consistency**:
  - 2023: Ranged from **43 to 98 admissions**.
  - 2024: Showed wider fluctuations, ranging from **74 to 135 admissions**.

### **2. Bed Occupancy Metrics**
- **Overall Bed Occupancy Rate**:
  - 2024: **65.63%**
  - 2023: **64.62%**
  - Slight increase of **1.01 percentage points**.
- **Departmental Changes**:
  - General Medicine: **86.54%** (down from **88.87%**, -2.33%).
  - Orthopedics: **56.03%** (up from **44.81%**, +11.22%).
  - Cardiology: **49.82%** (up from **42.97%**, +6.85%).
  - Pediatrics: **45.02%** (up from **42.34%**, +2.68%).
  - Surgery: **8.00%** (down from **10.00%**, -2.00%).

### **3. Admission Type Distribution**
- **2024**:
  - Inpatient: **676 admissions** (**68.94%**).
  - Outpatient: **306 admissions** (**31.16%**).
- **2023**:
  - Inpatient: **440 admissions** (**52.32%**).
  - Outpatient: **401 admissions** (**47.68%**).
- **Insight**: Shift towards more inpatient admissions in 2024.

### **4. Age Group Distribution**
- **65+ years**: Increased to **250** patients (up by **19%**).
- **50-64 years**: Increased to **236** patients (up by **20%**).
- **18-34 years**: Increased to **238** patients (up by **38%**).
- **Other Groups**: Slight changes in younger age groups, with a decline in ages 13-17.

### **5. Readmission Rates**
- **Overall**:
  - 2024: **15.68%**
  - 2023: **16.53%**
  - **Decrease of 0.85 percentage points**, indicating improved discharge planning and follow-up care.
- **Departmental Insights**:
  - Surgery: Dropped from **19.50%** to **7.27%** (**-12.23%**).
  - Obstetrics and Gynecology: Increased from **14.29%** to **19.05%** (**+4.76%**).
  - Cardiology: Decreased from **16.86%** to **15.64%** (**-1.22%**).

---

## **HEALTHCARE QUALITY METRICS**

### **1. Patient Safety Incidents**
- **Total Incidents Reported**:
  - 2023: **232 incidents**.
  - 2024: **161 incidents** (**-30.6% decrease**).
- **Top 5 Incident Types**:
  - Surgical site infections: Improved from **23** to **10 cases** (**-56.5%**).
  - Wrong dosage: Increased from **11** to **14 cases** (new concern).

### **2. Patient Satisfaction and Feedback**
- **Feedback Volume**:
  - 2023: **459 responses**.
  - 2024: **345 responses** (**-24.8% decrease**).
- **Satisfaction Score**:
  - Declined from **3.15 to 2.95** (on a 5-point scale), a **6.3% drop**.

### **3. Infection Control**
- **Overall Infection Rate**:
  - 2023: **29.31%**.
  - 2024: **21.74%**.
  - **Improvement of 7.57 percentage points**, a **25.8% reduction**.

---

## **STAFF PERFORMANCE AND UTILIZATION**

### **1. Workforce Distribution**
- **Doctors**: **14 staff members**.
- **Nurses**: **86 staff members**.
- **Total Staff**: **100 personnel**.

### **2. Staff-to-Patient Ratios**
- Doctors: **1:60**.
- Nurses: **1:10**.
- Overall: **1:12**, indicating balanced team structures.

### **3. Overtime and Absenteeism**
- **Overtime Hours**:
  - Doctors: **182.07 hours**.
  - Nurses: **201.87 hours**.
- **Absenteeism Rates**:
  - Doctors: **12%**.
  - Nurses: **14%**.
- **Correlation**:
  - Strong link between overtime and absenteeism, especially for doctors (**0.88 correlation coefficient**).

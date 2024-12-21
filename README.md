# Background and Overview

As a Data Analyst at Starlight General Hospital, I collaborated with the management and clinical teams to design a comprehensive dashboard aimed at enhancing decision-making across key areas of hospital operations. Starlight General Hospital is a 500-bed facility dedicated to delivering high-quality healthcare services while ensuring operational efficiency and staff optimization. This dashboard was developed to provide a data-driven approach to monitoring and improving patient care, safety, and staff performance.

## The primary goals of this project were to:
- Analyze and visualize patient management metrics to monitor admissions, readmission rates, and demographic trends.
- Evaluate the quality and safety of healthcare delivery through key performance indicators such as incident reporting, infection rates, and patient satisfaction.
- Assess staff performance and utilization to understand productivity and its impact on patient outcomes.

The dashboard is structured into three interconnected pages, each addressing a specific aspect of hospital operations:
- **Patient Management Overview**: Provides insights into patient inflow, demographics, and the efficiency of bed occupancy and admissions.
![image](https://github.com/user-attachments/assets/de7beba8-0789-45af-8b6a-32df23388d3e)

- **Healthcare Quality Metrics**: Tracks healthcare delivery quality by monitoring incidents, protocol adherence, and patient satisfaction scores.
![image](https://github.com/user-attachments/assets/82637d1f-c793-4e73-abcc-ca48ddc6cacd)

- **Staff Performance and Utilization**: Evaluates staff productivity, absenteeism, and the relationship between staffing levels and patient outcomes.
![image](https://github.com/user-attachments/assets/94beb116-a6ea-4cb3-8c25-e0a6354b9502)

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
![image](https://github.com/user-attachments/assets/37fd35c0-ba41-45c8-9773-72019403e319)
- **Total Admissions**: Increased to **982** in 2024 from **841** in 2023, representing a **14.4% growth**.
- **Peak Admission Months**:
  - 2024: March saw a peak with **135 admissions**.
  - 2023: November peaked at **98 admissions**.
- **Monthly Volume Consistency**:
  - 2023: Ranged from **43 to 98 admissions**.
  - 2024: Showed wider fluctuations, ranging from **74 to 135 admissions**.

### **2. Bed Occupancy Metrics**
![image](https://github.com/user-attachments/assets/6cd0b982-c754-4eab-9436-75785630dd49)

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
![image](https://github.com/user-attachments/assets/90459b6d-d80f-4fa3-aae0-a651c87e19ad)

- **2024**:
  - Inpatient: **676 admissions** (**68.94%**).
  - Outpatient: **306 admissions** (**31.16%**).
- **2023**:
  - Inpatient: **440 admissions** (**52.32%**).
  - Outpatient: **401 admissions** (**47.68%**).
- **Insight**: Shift towards more inpatient admissions in 2024.

### **4. Age Group Distribution**
![image](https://github.com/user-attachments/assets/6c4cde83-1bdd-4501-ab07-4420fd9c2be5)

- **65+ years**: Increased to **250** patients (up by **19%**).
- **50-64 years**: Increased to **236** patients (up by **20%**).
- **18-34 years**: Increased to **238** patients (up by **38%**).
- **Other Groups**: Slight changes in younger age groups, with a decline in ages 13-17.

### **5. Readmission Rates**
![image](https://github.com/user-attachments/assets/d9b35314-853f-4762-a129-6721e902ff46)

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
![image](https://github.com/user-attachments/assets/8eb474bd-c24e-469f-b3f4-6978c33acb41)

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
  ![image](https://github.com/user-attachments/assets/0d196316-0a5b-4637-acf3-e01525875618)

 
# Key Findings

## **Patient Management and Overview**
### **Admission Trends and Volume**
The hospital experienced significant growth in total admissions between 2023 and 2024, indicating increased patient trust or expanded service capacity. However, the shift in peak admission months suggests seasonal or operational changes that may need further investigation. For instance, while 2023 had a consistent flow, 2024 displayed notable fluctuations, hinting at factors like seasonal demand, marketing efforts, or staffing capacity influencing patient volumes.

### **Bed Occupancy Metrics**
While the overall bed occupancy rate remained relatively stable, departmental trends revealed dynamic changes. Notably, the Orthopedics department saw a remarkable increase, likely reflecting greater demand for its services or more efficient bed management. On the other hand, declines in Surgery and General Medicine occupancy might suggest changes in patient preferences, surgical scheduling, or outpatient treatment advancements reducing the need for inpatient care.

### **Admission Type and Demographics**
A sharp shift towards inpatient admissions in 2024 suggests the hospital is handling more complex cases requiring extended care. The demographic analysis shows growth in older and younger adult groups, reflecting a potential increase in chronic disease management and working-age population seeking care. Declines in certain age brackets, such as adolescents, may indicate shifts in healthcare utilization patterns or changing societal health trends.

### **Readmission Rates**
The reduction in overall readmission rates is an encouraging sign of improved discharge protocols and follow-up care. However, significant variations across departments highlight areas requiring targeted interventions. The dramatic reduction in the Surgery department's readmission rate suggests effective implementation of post-surgical care protocols, while the rise in Obstetrics and Gynecology's rate may warrant a closer look at maternity care practices or patient education.

---

## **Healthcare Quality Metrics**
### **Patient Safety**
The sharp decline in reported safety incidents is an important achievement, showcasing improvements in clinical processes or adherence to safety protocols. However, the rise in "wrong dosage" incidents indicates a new area of concern that should be prioritized for mitigation. Ensuring staff are trained on accurate medication administration is critical to maintaining trust and minimizing adverse outcomes.

### **Patient Satisfaction**
Declining patient satisfaction scores, despite fewer reported incidents, suggest a potential gap in service quality or patient experience management. This could stem from factors like staff shortages, communication issues, or increased patient loads, requiring a holistic review of patient interactions and service delivery models.

### **Infection Control**
The significant reduction in infection rates demonstrates excellent progress in hygiene and infection control measures. This success highlights the hospital’s ability to adapt to and mitigate infectious risks, an essential metric for both patient outcomes and public health credibility.

---

## **Staff Performance and Utilization**
### **Staffing Distribution**
The tiered staffing structure reflects a deliberate strategy to optimize patient care. Higher nursing allocations in Orthopedics and General Medicine align with these departments' higher physical care demands. However, smaller teams in Pediatrics and OB-GYN may signal an opportunity to reallocate resources to better meet patient needs in these departments.

### **Overtime and Burnout**
High overtime hours among nurses, combined with a stront correlation between overtime and absenteeism, point to potential burnout risks. Addressing this issue could improve staff well-being and patient care quality. The data suggests that nurses bear a heavier workload, which could strain resources and impact morale if not managed proactively.

---

# Recommendations

## **Patient Management and Overview**

### **1. Enhance Admission Flow Management**
To address the fluctuations in admission volumes observed in 2024, the hospital should:
- Implement predictive analytics tools to anticipate seasonal admission surges.
- Optimize staff scheduling during peak months like March to ensure adequate patient care.
- Review marketing strategies or outreach programs that may have contributed to inconsistent patient volumes.

### **2. Targeted Improvement in Bed Utilization**
- Reassess departmental bed allocation, especially in Surgery and General Medicine, where occupancy rates have declined.
- Explore options to expand Orthopedics and Cardiology capacity to match their increased demand.
- Introduce dynamic bed management systems to improve overall occupancy efficiency.

### **3. Focused Outreach for Age Groups**
- Develop targeted health campaigns for growing age demographics, such as the 18-34 and 50-64 age groups.
- Investigate reasons for declining admissions among adolescents (13-17) and tailor services to meet their needs.
- Enhance pediatric services to attract more young families, leveraging the slight growth in this category.

### **4. Minimize Readmissions**
- Conduct detailed reviews of post-discharge protocols in Obstetrics and Gynecology to reduce its rising readmission rates.
- Expand the successful post-surgical care strategies from the Surgery department to other areas.
- Strengthen patient education programs to improve adherence to follow-up care recommendations.

---

## **Healthcare Quality Metrics**

### **1. Address Patient Safety Concerns**
- Prioritize training sessions to tackle rising "wrong dosage" incidents, focusing on medication administration accuracy.
- Implement a robust digital medication management system to reduce human error.
- Continue reinforcing infection control protocols that have yielded excellent results.

### **2. Revitalize Patient Satisfaction Initiatives**
- Conduct patient surveys to identify specific drivers behind declining satisfaction scores.
- Enhance communication channels between patients and staff to foster trust and transparency.
- Invest in staff training focused on patient interaction and empathy.

### **3. Strengthen Feedback Mechanisms**
- Encourage higher feedback submission rates by simplifying feedback forms and introducing incentives for patients.
- Use feedback data to address service pain points, especially in departments with high readmission rates or declining satisfaction.

---

## **Staff Performance and Utilization**

### **1. Optimize Staffing Levels**
- Reassess staffing ratios in high-demand areas like Orthopedics and General Medicine to avoid overburdening nurses.
- Allocate additional resources to Pediatrics and OB-GYN departments to enhance service delivery.

### **2. Mitigate Burnout**
- Introduce flexible scheduling or additional hires to reduce nurse overtime and absenteeism.
- Provide mental health support and wellness programs to improve overall staff morale.

### **3. Explore Technology Solutions**
- Deploy automated workload distribution tools to optimize staff allocation and prevent bottlenecks.
- Invest in cross-training programs for staff to improve adaptability and cover for absenteeism more effectively.

---

## **Strategic Improvements**

### **1. Explore Revenue Growth Opportunities**
- Introduce value-added services tailored to growing demographics like chronic disease management for the 50-64 age group.
- Launch family-centric healthcare packages targeting pediatric and young adult patients.

### **2. Data-Driven Decision-Making**
- Utilize advanced analytics to continually monitor and optimize operational performance.
- Invest in a hospital-wide dashboard to track metrics like patient satisfaction, readmission rates, and staff utilization in real time.

### **3. Focus on Continuous Improvement**
- Establish a quality improvement task force to identify and address underperforming areas.
- Regularly review the impact of implemented strategies to ensure long-term success.

# Caveats and Assumptions (Bonus Section)

### **1. Data Limitations**
- The analysis relies on the assumption that all recorded data is accurate and complete. However, inconsistencies or errors in data entry may impact findings. 

### **2. Missing or Nonsensical Data**
- Some patient records had missing demographic details or nonsensical values (e.g., negative age), which were excluded from the analysis, potentially skewing results.

### **3. Sample Size Concerns**
- Certain segments, like the adolescent group (13-17 years), had smaller sample sizes, limiting the reliability of trends or insights derived for these categories.

### **4. Real-World Data Challenges**
- Acknowledging that real-world datasets are often imperfect, the findings should be interpreted with caution and validated against additional data or future trends.

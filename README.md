# 🏋️‍♀️ CrossFit Games Data Analytics Dashboard

## 📘 Overview
This Power BI project analyzes CrossFit Games athlete performance, affiliate success, and regional participation.  
It uses a **star schema data model** and DAX measures to evaluate competitiveness, affiliate strength, and participation patterns across gender and age groups.

---

## 🎯 Objectives
- Measure global CrossFit participation and performance.  
- Identify top-performing athletes, affiliates, and countries.  
- Evaluate gender and age-group performance.  
- Provide data-driven recommendations for athlete development and affiliate expansion.

---

## 🧩 Data Model
The model follows a **star schema** centered on `Fact Scores`.  
Bridge tables were created because **Athletes** and **Countries/Affiliates** had no direct link.

| Table | Description |
|--------|-------------|
| `Fact Scores` | Holds athlete ranks, workout scores, and points |
| `Athletes` | Athlete demographics (gender, age, weight, etc.) |
| `Affiliates` | Gym details (affiliate name, location) |
| `Countries` | Country details |
| `AthletesAffiliate` | Bridge between Athletes and Affiliates |
| `AthletesCountry` | Bridge between Athletes and Countries |

### Relationships
- `Athletes[Competitor_ID]` → `Fact Scores[Competitor_ID]`  
- `Fact Scores[Affiliate_ID]` → `Affiliates[Affiliate_ID]`  
- Bridge tables connect Athletes ↔ Affiliates and Athletes ↔ Countries.

---

## 📊 Dashboards

### **1. Executive Dashboard**
- Competitor count by country  
- Top countries by total points  
- Total affiliates by country  
- Average points per country  

### **2. Affiliate Dashboard**
- Average athletes per affiliate  
- Affiliate performance score (inverted average rank)  
- Total points by affiliate  
- Top affiliates by number of athletes  

### **3. Athlete Performance Dashboard**
- Top 10 competitors by points  
- Total points and average rank by age group  
- Average rank across weight groups  
- Country and affiliate of top performer  

### **4. Gender Insights Dashboard**
- Total athletes by gender  
- Total points by gender  
- Average rank comparison (M vs F)  

---

## ⚙️ Key DAX Measures

| Measure | Description |
|----------|--------------|
| `Total Points` | SUM of all points earned by athletes |
| `Average Rank per Competitor` | Average of cleaned workout ranks |
| `Affiliate Performance Score` | (Max Rank + 1) - Average Rank |
| `Average Athletes per Affiliate` | COUNTROWS(Athletes) / DISTINCTCOUNT(Affiliates) |
| `Top Competitor Name` | Athlete with highest total points |
| `Top Competitor Country` | Country of top athlete |
| `Top Competitor Affiliate` | Gym of top athlete |

---

## 🧠 Insights
- The U.S. dominates athlete participation and affiliate distribution.  
- A few affiliates produce a large share of top athletes.  
- Young athletes (15–24) show potential but need structured mentorship.  
- Male participation is higher, but female athletes show stronger consistency.  
- Data gaps exist in affiliate naming and country classification.

---

## 💡 Recommendations
- Expand talent pipelines in key non-U.S. regions (U.K., Canada, Australia, Iceland).  
- Learn from elite affiliates’ training systems (e.g., CrossFit Mayhem).  
- Pair young athletes (15–24) with experienced competitors for mentorship.  
- Improve injury prevention and preparation programs to reduce attrition.  
- Incentivize affiliate expansion in underrepresented regions.  
- Reassess and clean missing or unnamed affiliate data.

---

## 🧰 Tools & Techniques
- **Power BI Desktop (2025)** – Dashboard creation  
- **Excel** – Data preprocessing  
- **DAX** – Calculated columns and measures  
- **Star Schema Modeling** – Efficient relational structure  
- **Data Visualization** – Bar, line, KPI, and tooltip visuals  

---

## 🗂️ Repository Structure

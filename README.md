
# 🏘️  Residential Real Estate Analysis 

## 🚀 Executive Summary

This analysis explores residential real estate investment opportunities in **Minneapolis** vs. **Saint Paul, Minnesota**, using predictive modeling, yield analysis, and data transformation workflows.  

📌 It blends **machine learning, domain logic, and investor-first storytelling** to identify undervalued homes and rank the most promising targets for return.  

- 🧠 **Goal**: Use structured data to unlock investment opportunity in two midwestern metro markets  
- 📈 **Methods**: Regression modeling, valuation delta scoring, ETL automation  
- 💡 **Key Finding**:  
   - *Minneapolis* demonstrates stronger consistency in ROI across neighbourhoods  
   - *Saint Paul* presents deeper underpricing in select pockets  
- 📊 [Interactive Dashboard →](https://public.tableau.com/app/profile/adrian.santos8881/viz/MSP_final_20240312/Undervaluedpropertieswithinvestmentyield?publish=yes)

---

## 🎯 Purpose

1. Predict home sale prices using similar recently sold properties  
2. Flag under-valued homes using price prediction differentials  
3. Compare annual rental yield vs. property price  
4. Provide data-driven investment tools for market comparison  
5. Determine which city offers a more resilient long-term investment landscape

---

## ⚙️ Technical Stack

- **Python** for ETL, modeling, and automation  
- **Pandas**, **Scikit-learn**, **Jupyter Notebooks**  
- **Tableau** for interactive visualization  
- **Zillow API**, **public property data**  
- **Scrapeak API** for programmatic listing extraction  

---

## 🧠 Key Insights

- **Undervaluation Gap**: Dozens of properties showed $30K–$75K price gaps vs. model prediction  
- **Rental Yield Overlay**: Strong correlation between pricing inefficiency and rent-to-price ratio  
- **Model Performance**: Regression accuracy improved from 0.39 (baseline) to 0.52 after feature engineering  
- **Market Split**:  
  - Minneapolis = broader predictability, better rent performance  
  - Saint Paul = spikier data but higher-value outliers

---

## 📊 Tableau Dashboard

🔗 [Undervalued Properties with Investment Yield →](https://public.tableau.com/app/profile/adrian.santos8881/viz/MSP_final_20240312/Undervaluedpropertieswithinvestmentyield?publish=yes)

---

## 🎥 Presentation Materials

- 📽️ [Self-Running Presentation (.mp4)](./Project4_Presentation_movie_20240312.m4v)  
- 📄 [Slide Deck (.pdf)](./Project4_Presentation_20240312.pdf)

---

## 🔮 Roadmap & Expansion Ideas

1. **📆 Weekly ETL Snapshots**  
   Automate weekly data extraction to track active listings and pricing trends over time. Enables time-series forecasting of local markets.

2. **📍 Zip Code & Cluster Segmentation**  
   Use clustering and geo-analysis to surface local patterns. Identify ROI clusters and high-yield neighbourhoods.

3. **🏠 Rental Market Yield Model**  
   Build a separate predictive model for rent. Compare it to Zillow’s RentZestimate and integrate rental ROI into investment scoring.

4. **📊 "Comps Engine" for Price Validation**  
   Surface 3–5 similar sold listings per property. Compare model price vs. comps vs. market price to build investor confidence.

5. **🧪 Alt Property Types**  
   Explore smaller homes (1–2 beds) or duplexes. These may deliver higher returns and serve overlooked investor niches.

6. **📉 Residual Analysis**  
   Audit underperforming model segments. Add new features (e.g., HOA status, WalkScore, commute time) to tighten prediction variance.

7. **📦 Investor-Facing Tool Prototype**  
   Package the system into a lightweight tool: paste a listing → get price prediction, rental yield, and ROI score. Enable real estate investors to move fast, with confidence.

---

## 📂 Repository Overview

- `notebooks/` – Feature engineering, experiments, evaluation  
- `etl/` – Zillow data ingestion, filtering, cleaning scripts  
- `assets/` – Decks, visuals, Tableau links  
- `README.md` – This summary and growth-oriented documentation

---

## 🧾 Attribution

Originally developed as a capstone project, this analysis is now part of **GIGO Data, Inc.**'s prototype archive. It represents a **data-to-decision product lens**, blending technical accuracy with strategic clarity for investment applications.

---

## 👤 Contact

**Adrian Wise Santos**  
Founder & Head of Product, Growth  
📫 adrian.santos@gigodata.com  
🌐 [www.gigodata.com](https://www.gigodata.com)  
🔗 [LinkedIn](https://www.linkedin.com/in/adriansantos)  
☎️ +181-GIGO-DATA (+1-814-446-8232)

---

## 🏷️ Tags

`#GrowthProductManagement` `#RealEstateAnalytics` `#DataScience` `#Python` `#InvestmentModeling` `#ETL` `#Zillow` `#GIGOData` `#Tableau` `#AppliedMachineLearning`

**Author:** Adrian Wise Santos  
**v1.0.1 – Updated:** 2025-07-20  
**v1.0 – Published:** 2024-03-12

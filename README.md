# Customer Segmentation Using Clustering Techniques
## A Survey-Based Analysis of Fashion Consumer Shopping Behaviour
### BUSI1783 — Business Analytics Project
### MSc Business Analytics | University of Greenwich | 2025–2026

---

## Project Overview

This project applies four unsupervised machine learning clustering 
algorithm families to independently collected primary survey data 
from 381 fashion consumers, identifying three distinct customer 
segments and deriving actionable business recommendations for 
fashion retailers.

**Student:** Amareshwari Boini  
**Student ID:** 001488530  
**Programme:** MSc Business Analytics  
**Module:** BUSI1783 — Business Analytics Project  
**Supervisor:** Dr. Shoaib Haq  
**Institution:** University of Greenwich  
**Submission Date:** 27 August 2026  

---

## Research Question

What distinct customer segments exist among fashion consumers 
based on their behavioural and demographic characteristics, 
and what actionable business insights can be derived from 
these segments to inform targeted marketing strategies 
for fashion retailers?

---

## Repository Contents

| File | Description |
|------|-------------|
| `README.md` | Project documentation |
| `fashion_consumer_survey_clean.csv` | De-identified primary survey dataset (381 rows, 17 variables) |
| `customer_analysis.py` | Full Python analysis script |
| `requirements.txt` | Python library dependencies |

---

## Dataset Description

- **Source:** Independently collected primary data via Google Forms
- **Collection Period:** 22–24 August 2026
- **Total responses received:** 385
- **Duplicate rows removed:** 4 (fully identical across all answers)
- **Rows in clean file:** 381
- **Valid responses after under-18 filter:** 358
- **Features:** 17 behavioural, attitudinal and demographic variables
- **Privacy:** All personally identifiable information including 
  email addresses and timestamps has been permanently removed. 
  This repository contains only the de-identified dataset.

---

## Survey Variables

| Variable | Type | Description |
|----------|------|-------------|
| age_group | Ordinal | Age bracket of respondent |
| gender | Nominal | Gender identity |
| monthly_income | Ordinal | Monthly income or allowance (£) |
| purchase_frequency | Ordinal | How often clothing is purchased |
| spend_per_purchase | Ordinal | Typical spend per clothing purchase (£) |
| shopping_location | Nominal | Online, in-store, or both |
| online_platforms | Nominal | Preferred online shopping platform |
| purchase_planning | Ordinal | How far ahead purchases are planned |
| sale_purchase_frequency | Ordinal | Frequency of buying during sales |
| sustainable_preference | Ordinal | Preference for sustainable brands |
| purchase_influence | Nominal | Primary purchase influence factor |
| brand_loyalty | Ordinal | Importance of brand loyalty |
| return_frequency | Ordinal | Frequency of returning items |
| brand_discovery | Nominal | How new brands are discovered |
| delivery_importance | Ordinal | Importance of fast delivery |
| influencer_following | Ordinal | Level of influencer engagement |
| social_media_purchase_likelihood | Ordinal | Likelihood of buying via social media |

---

## Methodology

### Preprocessing Pipeline
1. Removed Timestamp, Email address and Score columns
2. Removed 4 fully identical duplicate rows
3. Renamed 17 columns to standardised labels
4. Removed under-18 responses
5. Reassigned multi-select shopping location responses to Both equally
6. Replaced Option 1 with Other in platforms column
7. Mode imputation for missing values
8. Ordinal encoding for 12 ordered variables
9. Label encoding for 5 nominal variables
10. StandardScaler applied — mean=0, std=1
11. PCA applied — 11 components retain 80.24% variance

### Clustering Algorithm Families Applied

| Algorithm Family | Type | Parameters | Silhouette Score |
|-----------------|------|------------|-----------------|
| K-Means | Centroid-based | K=3, n_init=10 | 0.1100 Best |
| DBSCAN | Density-based | eps=0.5-3.0, min_samples=5 | N/A not suitable |
| Hierarchical/Agglomerative | Linkage-based | Ward linkage, K=3 | 0.0916 |
| GMM | Probabilistic | n_components=3 | 0.0552 |

### Cluster Validation Methods
- Elbow Method — visual inertia assessment
- Silhouette Coefficient — Rousseeuw (1987)
- Gap Statistic — Tibshirani, Walther and Hastie (2001)
- Kruskal-Wallis H tests — statistical validation across segments
- Adjusted Rand Index — agreement between K-Means and Ward partitions

---

## Results

### Three Customer Segments Identified

| Segment | Label | n | Percentage |
|---------|-------|---|------------|
| Cluster 0 | Aspiring Fashion Enthusiasts | 113 | 31.2% |
| Cluster 1 | Casual Budget Shoppers | 142 | 39.2% |
| Cluster 2 | Conscious Trend Followers | 107 | 29.6% |

### Segment Profiles Summary

**Aspiring Fashion Enthusiasts (n=113)**
- Higher income (£1,000–£2,000 per month)
- Monthly shoppers spending £50–£100 per purchase
- Brand loyal with moderate social media engagement

**Casual Budget Shoppers (n=142)**
- Low income (under £500 per month)
- Infrequent shoppers (every 2–3 months)
- Spend under £20, low brand loyalty

**Conscious Trend Followers (n=107)**
- Low income but highly engaged consumers
- Strongly prefer sustainable brands
- Very brand loyal, follow influencers regularly
- Always buy during sales events

---

## How to Run

### Option 1 — Google Colab (Recommended)
1. Upload fashion_consumer_survey_clean.csv to Colab files
2. Upload customer_analysis.py to Colab files
3. Run the script

### Option 2 — Local Environment
```bash
# Clone the repository
git clone https://github.com/YOUR_USERNAME/fashion-customer-segmentation-busi1783.git

# Navigate to directory
cd fashion-customer-segmentation-busi1783

# Install dependencies
pip install -r requirements.txt

# Run the analysis
python customer_analysis.py
```

---

## Key References

Rousseeuw, P.J. (1987) Silhouettes: a graphical aid to the 
interpretation and validation of cluster analysis. 
Journal of Computational and Applied Mathematics, 20, pp. 53-65.

Tibshirani, R., Walther, G. and Hastie, T. (2001) Estimating 
the number of clusters in a data set via the gap statistic. 
Journal of the Royal Statistical Society: Series B, 
63(2), pp. 411-423.

Ogunleye, B. (2023) An exploration of clustering algorithms 
for customer segmentation. Analytics, 2, pp. 809-823.

---

## Ethical Statement

This project was conducted in full compliance with the University 
of Greenwich Research Ethics guidelines. All survey data was 
collected anonymously with informed consent. No personally 
identifiable information is stored in this repository. The project 
complies with the UK Data Protection Act (2018) and GDPR principles.

University of Greenwich Ethics Training completed via BUSI1788.
Supervisor approval obtained prior to data collection.

---

## License

Submitted for academic assessment purposes only.
© 2026 Amareshwari Boini — University of Greenwich

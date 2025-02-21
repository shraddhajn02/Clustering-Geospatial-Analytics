# Clustering and Geospatial Analytics
Applied clustering &amp; geospatial analytics to assess flood risk and optimize insurance coverage. Using Precisely's Geoaddressing &amp; FloodRisk APIs, identified underinsured properties and segmented them into risk-based clusters to enhance policy pricing, risk mitigation, and upselling opportunities for insurers.

🏠 Clustering for Flood Risk for Montpelier, VT

📌 Project Overview

This project applies clustering and risk assessment techniques to analyze flood risks in Montpelier, VT. By integrating geospatial intelligence, flood risk data, and property characteristics, this analysis helps insurance companies identify underinsured properties and optimize their risk pricing strategies.

🎯 **Key Takeaways**<br>
✅ Flood Risk in Montpelier: The 2023 and 2024 floods caused significant economic and structural damage, highlighting the need for better risk assessment.<br>
✅ Geospatial Intelligence: Used Precisely's Geoaddressing & FloodRisk APIs for accurate location-based risk analysis.<br>
✅ Risk Segmentation: Applied K-Means clustering to categorize properties into five risk-based groups.<br>
✅ Underinsurance Detection: Computed Insurance-to-Value (ITV) ratios to highlight underinsured properties.<br>
✅ Data-Driven Insights: Helps insurers optimize policy pricing, underwriting, and upselling opportunities.<br>

***Project Workflow***

1. Data Acquisition and Processing
Dataset: Address Fabric dataset with 10,311 properties.
Geocoding: Standardized addresses using Precisely's Geoaddressing API.
Flood Risk Enrichment: Retrieved flood zone data via Precisely's FloodRisk API.
Final Dataset: 10,170 enriched records.

2. Data Cleaning and Validation
Duplicate removal: Checked for redundant PBKEY entries.
ZIP Code validation: Ensured all records belong to Montpelier (ZIP prefix 056).
Geographical consistency: Verified latitude/longitude bounds and state accuracy.
Structural data verification: Checked building construction type, roof cover, and property value.

3. Clustering-Based Risk Assessment
Feature Engineering: Selected key risk-related attributes, including:
Flood proximity: Distance to 100-Year Flood Zone.
Elevation: Address location elevation above sea level.
Property attributes: Construction type, exterior walls, market value.
Dimensionality Reduction: Applied Principal Component Analysis (PCA).
Clustering Model: Used K-Means Clustering to segment properties into five risk clusters.

4. Flood Risk and Insurance Implications
Cluster 1 (Low Risk): Highest elevation, farthest from flood-prone areas.
Cluster 2 (Low-Moderate Risk): Located near low-risk zones with better construction materials.
Cluster 3 (Moderate Risk): Near Winooski River, vulnerable to water damage.
Cluster 4 (Moderate-High Risk): Close to high-risk flood zones (AE category).
Cluster 5 (High Risk): Directly in FEMA’s high-risk flood zones.

5. Underinsurance Identification
Insurance-to-Value (ITV) Analysis:
ITV Ratio = Policy Value / Assessed Value.
Threshold: <80% indicates underinsurance.
Result: Identified several properties as underinsured, requiring coverage adjustments.

**Business Impact**

1. Better Flood Risk Pricing for Insurers
More accurate underwriting: Data-driven risk categorization prevents mispricing.
Targeted premium adjustments: High-risk properties can be priced accordingly.
2. Identifying Upselling Opportunities
Underinsured properties: Suggested coverage increases to reduce financial exposure.
Multi-policy bundling: Encouraging flood coverage additions in high-risk zones.
3. Risk Mitigation Strategies
Community-level flood management: Data supports resilience planning for Montpelier.
Reinsurance Partnerships: Insurers can leverage risk-sharing models for high-risk clusters.
Skills and Technologies Used

**Data Processing & Analysis:**
pandas, numpy: Data wrangling and transformations.
scipy.stats, sklearn.cluster: Clustering and statistical modeling.

**Geospatial Intelligence**
matplotlib, seaborn: Geospatial risk visualization.
Precisely Geoaddressing API: Address standardization and geocoding.
Precisely FloodRisk API: Flood zone data enrichment.

**Machine Learning for Clustering**
K-Means Clustering: Categorizing properties into risk-based groups.
Principal Component Analysis (PCA): Feature selection and dimensionality reduction.

**Insurance Risk Assessment**
Insurance-to-Value (ITV) Ratio Calculation: Detecting underinsured properties.
FEMA Flood Zone Classification: Risk mapping using FEMA flood zones.

**📂 Feature Engineering**
The project uses several key property and geospatial features to assess flood risk and insurance coverage gaps. These features help segment properties into meaningful clusters based on their vulnerability to flooding.

*Distance to 100-Year Flood Zone (Year100FloodZoneDistanceFeet)*
This metric determines how close a property is to FEMA’s 100-year floodplain (high-risk area).
Lower distance values indicate a higher flood risk, as properties in these zones are more susceptible to flooding events.

*Distance to Nearest Waterbody (DistanceToNearestWaterbodyFeet)*
This feature calculates a property's proximity to rivers, lakes, or other water bodies.
Properties closer to a water source are at higher risk of flooding, especially during heavy rainfall events or storm surges.

*Elevation Above Sea Level (AddressLocationElevationFeet)*
Elevation plays a critical role in flood vulnerability.
Lower elevation properties are more likely to experience flooding, while higher elevation properties have a natural barrier against water accumulation.

*Building Construction Type*
The material and design of a property impact its resilience to flood damage.
For example, wooden structures are generally more vulnerable compared to masonry or concrete buildings.

*Flood Zone Classification*
Each property is categorized into FEMA-defined flood zones, such as A, AE, X, and SHX, which indicate varying levels of risk.
AE zones are high-risk areas, requiring stricter insurance and mitigation strategies.

*Property Market Value*
The total assessed value of the property is used to evaluate underinsurance and assess potential financial risks for insurers.

**APIs Used:**

1. Precisely Geoaddressing API
Used for address validation and geocoding.
Ensures standardized, accurate property location data.

2. Precisely FloodRisk API
Provides flood zone classifications and risk scoring.
Helps determine proximity to water bodies and flood-prone areas.

3. Precisely PropertyAttributesByAddress API
Retrieves detailed property characteristics (e.g., construction type, assessed value, roof type) for deeper risk analysis.

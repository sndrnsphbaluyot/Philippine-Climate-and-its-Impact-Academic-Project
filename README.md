# There's Always Another Storm: How Climate Change Amplifies Risks in the Philippines
## Overview
Climate change has become one of the most significant challenges facing the Philippines, a country consistently ranked among the world's most climate-vulnerable nations. Rising temperatures, increasingly powerful typhoons, unpredictable rainfall patterns, accelerating deforestation, and sea-level rise are creating interconnected environmental risks that threaten communities, ecosystems, and economic stability.
This project explores how these climate indicators have changed between 2014 and 2023 and how they collectively contribute to the country's growing vulnerability. By combining multiple environmental datasets into an interactive Tableau dashboard, the project transforms complex climate data into an accessible and actionable data story for both technical and non-technical audiences.
## Table of Contents
- [Dataset Description](#dataset-description)
- [Column Definitions](#column-defenitions)
- [Tools Used](#tools-used)
- [Data Cleaning Methodology](#data-cleaning-methodology)
- [Project Overview](#project-overview)
- [Dashboard](#dashboard)
- [Key Insights](#key-insights)
- [Conclusion](#conclusion)
- [Data Sources](#data-sources)
- [License & Data Sources](#license-&-data-sources)

## Dataset Description
This project combines five environmental datasets that measure different aspects of climate change and environmental degradation in the Philippines from 2014 to 2023.
Datasets Used
1. Philippine Monthly Typhoon Trend (2014-2024)
Tracks annual typhoon activity and climate indicators influencing storm development.
2. PSA Temperature Monitoring Data
Contains temperature observations from monitoring stations across the Philippines.
3. PSA Rainfall Monitoring Data
Contains annual rainfall measurements collected from weather monitoring stations.
4. Deforestation in the Philippines
Measures annual tree cover loss across Philippine provinces.
5. Annual Mean Sea Level of Tide Stations
Tracks long-term sea-level changes at monitoring stations throughout the country.
## Key Characteristics
Coverage Period: 2014-2023
Geographic Scope: Philippines
Data Types:
Time-series environmental data
Geographic monitoring data
Provincial-level environmental records
Climate indicators and trends
Audience:
Students
Educators
Local communities
Government agencies
NGOs
Environmental researchers
## Column Definitions
<details>
  <summary> Since the project combines multiple datasets, the column structure varies by source. Click to expand column defenitions. </summary>

*Typhoon Dataset*
  | Column | Data Type | Description |
|---------|---------|-------------|
| Year | Integer | Observation year |
| Total_Typhoons | Integer | Total typhoons recorded during the year |
| Avg_ONI | Decimal | Average Oceanic Niño Index |
| Avg_Nino3.4_SST_Anomaly | Decimal | Average sea surface temperature anomaly |
| Avg_Western_Pacific_SST | Decimal | Average Western Pacific sea surface temperature |
| Avg_Vertical_Wind_Shear | Decimal | Average annual wind shear level |
| Avg_Midlevel_Humidity | Decimal | Average annual humidity level |
| Avg_SeaLevelPressure | Decimal | Average annual sea-level pressure |
| Avg_MJO_Phase | Decimal | Average Madden-Julian Oscillation phase |

**Temperature Dataset**
| Column | Data Type | Description |
|---------|---------|-------------|
| Year | Integer | Observation year |
| Month | String | Month of observation |
| Monitoring Station | String | Weather monitoring station name |
| Mean Temperature | Decimal | Average recorded temperature (°C) |

**Rainfall Dataset**
| Column | Data Type | Description |
|---------|---------|-------------|
| Year | Integer | Observation year |
| Monitoring Station | String | Rainfall monitoring station |
| Total Rainfall | Decimal | Total annual rainfall recorded (mm) |

**Deforestation Dataset**
| Column | Data Type | Description |
|---------|---------|-------------|
| Province | String | Philippine province |
| Area_HA | Decimal | Total provincial area in hectares |
| TC_Loss_HA | Decimal | Annual tree cover loss in hectares |
| Total_TC_Loss_2014_2023 | Decimal | Total tree cover loss accumulated between 2014 and 2023 |

**Sea-Level Dataset**
| Column | Data Type | Description |
|---------|---------|-------------|
| Year | Integer | Observation year |
| Tide Station | String | Coastal monitoring station |
| Mean Sea Level | Decimal | Annual mean sea level measurement |
</details>

## Tools Used
Microsoft Excel / Google Sheets
Used for:
Initial dataset review
Dataset verification
Manual inspection of records
Tableau Prep Builder
Used for:
Data cleaning
Data validation
Deduplication checks
Data aggregation
Format standardization
Handling missing values
Creating calculated fields
Tableau Public
Used for:
Interactive dashboard creation
Geographic visualization
Trend analysis
KPI reporting
Storytelling through data
Public dashboard hosting

## Data Cleaning Methodology
<details>
<summary>The datasets underwent extensive cleaning and preparation using Tableau Prep Builder before visualization. Click to expand the Data Cleaning Methodology. </summary>
  
### Handling Missing Values

- Typhoon Dataset
  - Reviewed all records for missing values
  - Excluded 2024 data to maintain consistency

- Temperature Dataset
  - Removed null temperature values
  - Removed note sections and irrelevant records
  - Retained only Mean Temperature observations
  - Excluded Maximum and Minimum temperature records

- Rainfall Dataset
  - Reviewed for "...", blanks, and null values
  - Removed invalid entries after aggregation

- Deforestation Dataset
  - Verified completeness
  - No missing values identified

- Sea Level Dataset
  - Filtered null values
  - Removed blank and invalid records
  - Retained only valid observations

### Duplicate Validation
All datasets were reviewed for duplicate records.
 
| Dataset | Duplicates Found |
|----------|------------------|
| Typhoon | None |
| Temperature | None |
| Rainfall | None |
| Deforestation | None |
| Sea Level | None |

No duplicate records were identified across any of the datasets; therefore, no duplicate removal actions were required.

### Standardizing Formats
- Temperature Dataset
Renamed source table field to Year
Pivoted monthly columns into a Month field
Converted temperatures to numeric datatypes

- Rainfall Dataset
Standardized year formats
Converted rainfall values to numerical formats

- Deforestation Dataset
Removed unnecessary spaces in province names

- Sea Level Dataset
Verified consistency after cleaning

### Data Aggregation and Transformation
- Typhoon Dataset
The original dataset contained monthly observations.
Transformations included:
Summed monthly typhoon counts into annual totals
Renamed:
 - Number_of_Typhoons → Total_Typhoons
Averaged climate indicators:
 - ONI
 - SST anomalies
 - Humidity
 - Wind shear
 - Sea level pressure
Result:
 - One record per year
 - Easier trend analysis
   
- Deforestation Dataset
Multiple municipal-level records existed for some provinces.
Actions:
 - Grouped by Province and Area_HA
 - Summed annual Tree Cover Loss values
Created:
 - Total_TC_Loss_2014_2023
Result:
 - One consolidated record per province
</details>

### Data Integrity Validation
Validation checks included:
- Year range verification (2014-2023)
- Completeness assessment
- Null value review
- Station count verification
- Consistency checks across locations
- Verification of calculated fields
- The final datasets were complete, consistent, and visualization-ready.

## Problem Statement
The Philippines experiences recurring climate-related disasters including typhoons, flooding, coastal erosion, rising temperatures, and forest degradation.
While these issues are often examined separately, this project investigates how they interact as part of a larger climate-resilience challenge.

## Hypothesis
Climate change is creating a chain reaction of environmental impacts in the Philippines:
- Rising temperatures contribute to stronger storms.
- Stronger storms produce heavier rainfall.
- Deforestation increases vulnerability to flooding and erosion.
- Sea-level rise worsens coastal flooding.
These drivers collectively increase disaster risk nationwide.

## Assumptions
The selected datasets accurately represent national climate conditions.
Historical trends can provide insight into future climate risks.
Data cleaning processes removed significant inconsistencies without altering true trends.

## Dashboard
Tableau Public Dashboard
🔗 [Philippine Climate and its Impact (Data Visualization Techniques Course Project)](https://public.tableau.com/views/PhilippineClimateanditsImpactDataVisualizationTechniquesCourseProject/MainDashboard?:language=en-US&:sid=&:redirect=auth&:display_count=n&:origin=viz_share_link)
The dashboard consists of five primary sections:
- Typhoon Trends
- Temperature Patterns
- Rainfall Variability
- Tree Cover Loss
- Sea-Level Rise
  
Each dashboard includes interactive filters, maps, KPIs, and trend visualizations designed for both technical and non-technical users.

## Key Insights
1. Rising Temperatures Continue Across the Philippines
Average temperatures showed a clear upward trend between 2014 and 2023, supporting global warming patterns observed worldwide.
2. Stronger Climate Conditions Coincide with Increased Typhoon Activity
Years with warmer ocean conditions often aligned with higher typhoon counts, suggesting stronger climate influences on storm development.
3. Rainfall Has Become Increasingly Unpredictable
Rainfall patterns displayed more extreme fluctuations, increasing risks of both flooding and drought.
4. Deforestation Weakens Climate Resilience
Provinces such as Palawan and Agusan del Sur recorded substantial tree cover loss, reducing natural flood protection and increasing exposure to environmental hazards.
5. Sea Levels Continue to Rise
Monitoring stations reported gradual but persistent increases in sea level, highlighting growing risks to coastal communities.
6. Climate Risks Are Interconnected
The datasets reveal that climate change is not a collection of isolated events but a network of reinforcing environmental challenges.

## Conclusion
Climate change is no longer a future concern for the Philippines. The evidence from typhoon activity, temperature trends, rainfall variability, deforestation, and sea-level rise demonstrates that environmental risks are already increasing across the country.
By combining multiple datasets into a unified data story, this project highlights how climate impacts are interconnected and why resilience planning requires a holistic approach. The findings reinforce the importance of data-driven decision making, environmental protection, and community preparedness in addressing the country's growing climate challenges.
As the title of this project suggests, there will always be another storm. However, through informed action, better planning, and stronger environmental stewardship, the Philippines can build a more resilient future.

## License & Data Sources
Data Sources
- Magtibay, D. M. (n.d.). Philippines Monthly Typhoon Trend (2014-2024).[https://www.kaggle.com/datasets/denvermagtibay/philippines-monthly-typhoon-trend-2014-2024?resource=download](https://www.kaggle.com/datasets/denvermagtibay/philippines-monthly-typhoon-trend-2014-2024?resource=download)
- CPES | Philippine Statistics Authority. (2024, July 9).[https://psa.gov.ph/statistics/environment-statistics/node/1684064180](https://psa.gov.ph/statistics/environment-statistics/node/1684064180)
- CPES | Philippine Statistics Authority. (2024, July 9).[https://psa.gov.ph/statistics/environment-statistics/node/1684064180](https://psa.gov.ph/statistics/environment-statistics/node/1684064180)
- Vizzuality. (n.d.). Philippines deforestation Rates & Statistics | GNW.[https://www.globalforestwatch.org/dashboards/country/PHL/?location=WyJjb3VudHJ5IiwiUEhMIl0%3D](https://www.globalforestwatch.org/dashboards/country/PHL/?location=WyJjb3VudHJ5IiwiUEhMIl0%3D)
- CPES | Philippine Statistics Authority. (2024, July 9).[https://psa.gov.ph/statistics/environment-statistics/node/1684064180](https://psa.gov.ph/statistics/environment-statistics/node/1684064180)

License

This project is intended for educational and non-commercial purposes. All datasets remain the property of their respective authors, organizations, and data providers. Please refer to the original data sources for specific licensing and usage terms.

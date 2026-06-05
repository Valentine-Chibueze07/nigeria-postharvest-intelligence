# Nigeria-postharvest-intelligence
 Operational intelligence analysis of post-harvest agricultural losses across Nigeria's 6 geopolitical zones. 5,000 farmer records, 6 crop types, root-cause analysis, and strategic recommendations.



"Nearly 1 in 5 kilograms harvested never reaches a market. This project investigates why — and what can realistically be done about it."

by Iroagba Valentine Chibueze · Agricultural Data Intelligence · 2023–2024 Dataset

The Problem
Nigeria loses an estimated 40–50% of its agricultural produce annually to post-harvest challenges. For context: that is food produced, land used, water consumed, labour invested — and then lost between the farm and the consumer. For smallholder farmers operating on thin margins, a single spoilage event can erase an entire season's income.
This project focuses on a specific slice of that problem: analysing post-harvest loss patterns across 5,000 farming operations in Nigeria's six geopolitical zones to identify where losses are highest, what operational factors drive them, and which interventions — in what sequence — would produce the greatest impact.
The analysis was built to function as a decision-support system, not a reporting exercise. Every finding is evaluated through the lens of: what would a stakeholder need to know to make a better operational decision tomorrow?

Project Scope
DimensionDetailDataset5,000 farming operation recordsCoverage6 geopolitical zones (North Central, North East, North West, South East, South South, South West)Crop TypesCassava, Maize, Pepper, Rice, Tomato, YamVariables20 fields spanning storage, transport, environmental conditions, technology, training, and financial outcomesPeriod2023–2024 growing seasonsPrimary MetricPost-Harvest Loss Percentage (PHL%)Financial MetricRevenue Loss (NGN)

Project Objectives

Quantify the scale and distribution of post-harvest losses across Nigeria's regions and crop types
Identify the operational, environmental, and structural drivers of spoilage
Evaluate the measurable impact of technology adoption, training programmes, and youth participation
Assess logistics and storage method effectiveness
Generate prioritised, evidence-based recommendations for operational improvement
Deliver a professional analytics package usable by operational managers, agricultural programme officers, and executive stakeholders


Repository Contents
nigeria-postharvest-intelligence/
├── 01_data/
│   ├── raw/                          ← Original unmodified dataset
│   └── processed/                    ← Cleaned dataset + KPI framework + DAX measures
├── 02_analysis/
│   ├── eda_summary.md                ← Exploratory analysis findings
│   ├── data_cleaning_log.md          ← Cleaning decisions and rationale
│   └── kpi_definitions.md            ← KPI framework with business context
├── 03_dashboard/
│   ├── nigeria_phl_dashboard.html    ← Interactive browser dashboard
│   ├── nigeria_phl_dashboard.pdf     ← Static PDF version
│   ├── powerbi_build_guide.md        ← Power BI construction specification
│   └── screenshots/                  ← Dashboard page captures
├── 04_reports/
│   └── executive_report.docx         ← Full executive intelligence report
├── 05_visuals/
│   └── linkedin_infographic.png      ← Summary infographic
└── docs/
    ├── technical_documentation.md
    ├── portfolio_case_study.md
    └── project_methodology.md

Analytical Methodology
The analysis followed a structured operational intelligence workflow rather than a linear data science pipeline. The distinction matters: this project was not about applying a method — it was about answering a specific business question through a sequence of investigative steps.
Phase 1 — Data Understanding
Before any cleaning or analysis began, each variable was evaluated for its operational meaning, not just its data type. For example, Tech_Used had a 60.3% null rate — a figure that, in isolation, looks like a data quality problem. In operational context, it represents farmers with no recorded technology use, which is itself a finding of significance. That distinction shaped how the null handling was approached.
Phase 2 — Data Cleaning & Validation
An 18-point validation protocol was applied:

Logical consistency checks (spoilage cannot exceed total harvest)
Percentage boundary validation (PHL% cross-validated against computed ratio)
Environmental range validation (temperature and humidity within Nigerian tropical bounds)
Categorical standardisation across all text fields
Duplicate detection against the Farmer_ID primary key

Key decision: Null values in Tech_Used were standardised to "None" rather than imputed or dropped, preserving the operational signal that 3,017 farmers operate without post-harvest technology.
Phase 3 — KPI Engineering
Fifteen operational KPIs were designed, each evaluated for business relevance before inclusion. Metrics were built to answer specific operational questions rather than to populate a dashboard. Key examples:

PHL Rate = Spoilage ÷ Total Harvest × 100 (cross-validated against dataset field)
Technology Adoption Rate = Farmers with Tech_Used ≠ "None" ÷ Total Farmers
Training Impact Ratio = PHL (untrained) ÷ PHL (trained) — reveals intervention effectiveness
Revenue Loss per kg Spoiled = Total Revenue Loss ÷ Total Spoilage — captures economic severity

Phase 4 — Exploratory Analysis & Root-Cause Investigation
Analysis proceeded in concentric layers:

Aggregate performance (total KPIs)
Segmentation (by region, crop, storage method, transport mode)
Cross-segmentation (region × crop heatmap, storage × market access)
Environmental driver analysis (spoilage quartile vs temperature, humidity, storage duration)
Intervention analysis (technology, training, youth involvement)

At each layer, findings were evaluated for operational significance, not just statistical difference.
Phase 5 — Insight Generation & Recommendation Sequencing
Findings were translated into recommendations using an impact-urgency matrix. Recommendations were not simply listed — they were sequenced and costed against the operational realities identified in the data.

Key Findings
1. The scale of loss is systemic, not localised
The average PHL rate of 19.25% — nearly double the FAO benchmark of 10% — is consistent across all six geopolitical zones. North Central shows the lowest rate (18.83%) and North East the highest (19.57%), but no zone is close to acceptable performance. This is not a regional problem with regional solutions. It is a systemic operational challenge requiring coordinated intervention.
2. Pepper is the most financially damaging crop
Rice carries the highest PHL rate (19.58%), but Pepper generates the greatest absolute revenue loss at ₦12.9 million — 31.2% of total dataset losses. The combination of premium pricing and high perishability without cold chain infrastructure makes Pepper the highest-priority crop for market linkage and cold storage intervention.
3. Cold Storage is the most counterintuitive finding
Cold Storage is associated with the highest average PHL (19.39%) and among the highest revenue losses — despite being the most capital-intensive storage option available. This does not mean cold storage fails as a concept. It means cold storage is failing in execution: unreliable power supply, inadequate temperature control, and overcrowding are producing outcomes worse than simpler alternatives. Crates — a low-cost option prioritising airflow and physical separation — deliver the best observed PHL rate (19.00%). This finding has significant implications for infrastructure investment decisions.
4. Technology works, but coverage is critically low
Hermetic bag users show the lowest PHL rate (18.76%), mobile app users show the lowest revenue loss (₦7,940 average), and solar dryer users outperform the dataset average. Yet 60.3% of farmers — 3,017 operations — use no post-harvest technology whatsoever. The intervention gap is not a knowledge gap about what works. It is an access and distribution gap.
5. Training impact is negligible — and the reason matters
Trained farmers show an average PHL of 19.30% versus 19.23% for untrained farmers — a difference that is operationally meaningless. The instinctive response is to question the value of training. The more accurate interpretation is that training without tools produces no measurable outcome. Knowledge of correct post-harvest practices is insufficient when the equipment to apply those practices is unavailable. This finding argues for bundled intervention: training and technology delivered together.
6. Transport mode is a significant and addressable driver
Truck transport delivers the lowest PHL (18.82%) and lowest revenue loss (₦7,917 average). Motorcycle transport — used by a substantial portion of the dataset — shows a PHL of 19.39% and the highest average revenue loss (₦8,711). The gap is not explained by distance alone. Exposure time, vibration, and lack of load protection during motorcycle transport are amplifying spoilage before produce reaches the market.
7. Environmental conditions are above optimal thresholds everywhere
The dataset-wide average temperature of 29.9°C and humidity of 60.2% both exceed the optimal ranges for produce storage and transport. More critically, the high-spoilage quartile shows temperatures nearly 2°C higher and humidity 6.5 points higher than the low-spoilage quartile. Environmental management — through shading, ventilation, and timing of transport — is a low-cost operational intervention with immediate potential impact.

Summary KPI Table
MetricValueBenchmarkStatusTotal Harvest Volume1,004,961 kg—BaselineTotal Spoilage193,071 kgMinimise⚠Average PHL Rate19.25%< 10%🔴 CriticalTotal Revenue Loss₦41,415,461Minimise🔴 CriticalAvg Revenue Loss / Farmer₦8,283Minimise⚠Technology Adoption Rate39.7%> 70%⚠Training Participation Rate28.9%> 60%🔴 CriticalYouth Participation Rate39.9%> 50%⚠Avg Storage Duration10.0 days< 7 days⚠Avg Temperature29.9°C< 25°C🔴 CriticalAvg Relative Humidity60.2%< 55%⚠

Strategic Recommendations
Immediate (0–3 Months)
#InterventionRationaleExpected Impact01Scale hermetic bag distribution to North East, South West, North West zonesHighest PHL reduction per investment of any technology in datasetPHL reduction to ~18.76% for adopters02Emergency training scale-up bundled with equipment in high-risk zonesTraining alone shows negligible impact; tools + training together is the operative modelCoverage: 28.9% → 60%+ within one season
Medium-Term (3–12 Months)
#InterventionRationaleExpected Impact03Cold storage infrastructure audit and remediationCold storage currently produces the worst outcomes of any storage method — a quality failure, not a concept failurePotential recovery from 19.39% to sub-17% PHL for participating facilities04Community truck cooperative model — aggregation hubs every 10–15 kmMotorcycle and bicycle transport are the highest-risk, highest-loss modes; cooperative trucking resolves this without requiring individual capital investmentPHL: 19.39% → 18.82%; ₦794 average revenue recovery per farmer05Mobile agricultural platform deployment with subsidised rural data accessMobile app users already show the lowest revenue loss; expanding digital access scales this effect at near-zero marginal costScalable; compound network benefit as platform user base grows
Strategic (12–36 Months)
#InterventionRationaleExpected Impact06Youth agricultural enterprise programme with integrated support packageYouth-involved operations underperform due to structural constraints, not operational failures; the correct response is a support ecosystem, not reduced youth participationConverts the largest at-risk cohort into the primary long-term productivity driver07Solar dryer expansion for Tomato, Pepper, and Cassava farmersEnables value-added processing, longer shelf life, and premium market access; directly addresses the highest revenue-loss crop typesDual impact: spoilage reduction and farmer income diversification08Regional post-harvest intelligence centres in North East, South West, and North WestPermanent institutional capacity for data collection, intervention coordination, and performance monitoring at the zone levelFoundational infrastructure for sustained, adaptive, evidence-based agricultural improvement

Tools Used
ToolApplicationMicrosoft ExcelData cleaning, KPI framework, DAX documentationPython (pandas, openpyxl, reportlab)Data processing, Excel workbook generation, PDF report generationChart.jsInteractive HTML dashboard visualisationsHTML/CSS/SVGDashboard layout, LinkedIn infographicPower BI (spec)Dashboard architecture and DAX measure designMicrosoft Word (docx.js)Executive intelligence report generation

Limitations & Honest Caveats
What this analysis cannot claim:

The differences observed across groups (e.g., technology types, transport modes) have not been formally tested for statistical significance. The sample sizes within some subgroups are sufficient for operational conclusions but would benefit from hypothesis testing before policy-level decisions are made solely on this basis.
The dataset is cross-sectional. It captures a moment in time, not a trend. Whether conditions are improving or deteriorating requires longitudinal data.
No external validation data (market prices, weather station records, policy timelines) was integrated. Enriching this dataset with external sources would substantially strengthen the causal reasoning.
The training effectiveness finding (negligible PHL difference) is plausible but cannot be definitively explained without training recency, content quality, and post-training follow-up data.


Future Development

Version 2.0: Integrate statistical significance testing (chi-square, ANOVA) across key segmentation variables
Version 2.1: Build predictive model (regression or decision tree) to identify the strongest independent predictors of PHL
Version 2.2: Enrich dataset with external FEWS NET price data, NIMET weather records, and NAFDAC cold storage registry
Version 3.0: Deploy as a live Power BI Service dashboard with scheduled data refresh
Extended scope: Expand to include post-harvest loss economic modelling — estimating the full agricultural GDP impact at state and national level


About the Author
Iroagba Valentine Chibueze is an aspiring data analyst with a Petroleum Engineering background. His work sits at the intersection of operational intelligence, systems thinking, and data-driven problem-solving — with a particular focus on how analytical frameworks can address real-world operational challenges in Nigerian and African economic contexts.
Skills: SQL Server · Power BI · Excel Analytics · Python (pandas, data processing) · Business Intelligence · Operational Analytics


This project is part of an ongoing analytics portfolio documenting operational intelligence work across Nigerian economic and industrial contexts.
Dataset contains anonymised operational records. No personally identifiable information is included.

\# Patiala Flood Intelligence — System Contract



\## 1. Project Identity



Project Name:

Patiala Flood Intelligence



Purpose:

Build an AI-powered urban flood and waterlogging intelligence and decision-support system.



The system converts environmental, geographic, infrastructure, and historical data into:



\- Flood/waterlogging risk intelligence

\- Spatial risk zones

\- Infrastructure impact assessment

\- Population/area impact assessment

\- Explainable risk factors

\- Actionable recommendations

\- Scenario simulations

\- A unified operational dashboard





\## 2. Geographic Scope Lock



\### CURRENT OPERATIONAL SCOPE



The system starts with:



Patiala, Punjab, India.



For the current project and prototype, all:



\- Data

\- Models

\- Predictions

\- Maps

\- Infrastructure analysis

\- Risk calculations

\- Scenario simulations

\- Recommendations

\- Dashboard views

\- Testing

\- Validation



must remain focused on Patiala.



\### IMPORTANT



The architecture MUST be scalable to support other cities in the future.



However:



NO expansion beyond Patiala is permitted by default.



The system must NOT automatically:



\- Add other cities

\- Download datasets for other cities

\- Create multi-city dashboards

\- Change the model to multi-city operation

\- Add geographic regions outside Patiala

\- Generalize the UI to multiple cities

\- Change the database scope



unless P6 / Architecture Lead explicitly authorizes the expansion.



Future geographic expansion requires an explicit decision.



Current rule:



Patiala only → until explicitly authorized otherwise.





\## 3. Long-Term Geographic Vision



The intended progression is:



Patiala

&#x20;   ↓

Other Indian Cities

&#x20;   ↓

India

&#x20;   ↓

Global Urban Flood Intelligence



This is a FUTURE direction, not part of the current prototype scope.



The current implementation must optimize for Patiala while avoiding architectural decisions that make future expansion unnecessarily difficult.





\## 4. Core System Objective



The system should answer five questions:



1\. What is happening?

2\. Where is the risk?

3\. Why is the area at risk?

4\. What could be affected?

5\. What should decision-makers do?





\## 5. Core System Flow



Weather / Rainfall

&#x20;       ↓

Data Pipeline

&#x20;       ↓

Risk Engine

&#x20;       ↓

Spatial Risk Zones

&#x20;       ↓

Infrastructure / Population Impact

&#x20;       ↓

Decision \& Recommendation Engine

&#x20;       ↓

Operational Dashboard





\## 6. High-Level Architecture



Data Sources

&#x20;       ↓

Data Pipeline

&#x20;       ↓

PostgreSQL + PostGIS

&#x20;       ↓

&#x20;┌───────────────┬───────────────┐

&#x20;↓               ↓

AI Risk Engine   GIS / Impact Engine

&#x20;↓               ↓

&#x20;└───────────────┴───────────────┐

&#x20;                                ↓

&#x20;                          FastAPI Backend

&#x20;                                ↓

&#x20;                       Recommendation Engine

&#x20;                                ↓

&#x20;                        React Dashboard

&#x20;                                ↓

&#x20;                           MapLibre





\## 7. Recommended Technology Stack



\### Frontend

React + Vite

Tailwind CSS

MapLibre GL JS

Recharts / ECharts



\### Backend

Python

FastAPI



\### Database

PostgreSQL

PostGIS



\### Data Processing

Python

Pandas

GeoPandas



\### AI / Machine Learning

XGBoost or Random Forest for initial structured-data modelling.



The project must prioritize explainable and defensible modelling over unnecessary model complexity.





\## 8. Data Sources



Potential data sources include:



\### Weather / Rainfall

\- Open-Meteo

\- India Meteorological Department

\- NASA GPM IMERG



\### Geographic / Terrain

\- Copernicus DEM

\- ISRO / Bhuvan



\### Roads / Infrastructure

\- OpenStreetMap

\- Overpass API

\- Government/open datasets where available



\### Historical Flood / Waterlogging

\- Government records

\- Disaster management records

\- Municipal records where available

\- Research datasets

\- Satellite-derived observations

\- Credible historical reports



Data source selection must consider:



\- Accuracy

\- Availability

\- Geographic coverage

\- Temporal coverage

\- Licensing

\- Reproducibility





\## 9. Data Pipeline



Raw data must NOT be directly consumed by the AI model.



Required flow:



Raw Data

&#x20;   ↓

Validation

&#x20;   ↓

Cleaning

&#x20;   ↓

Standardization

&#x20;   ↓

Feature Engineering

&#x20;   ↓

Processed Data

&#x20;   ↓

Database / Model





\### Preprocessing may include:



\- Missing-value handling

\- Duplicate removal

\- Unit normalization

\- Timestamp normalization

\- Coordinate normalization

\- Geographic projection handling

\- Naming standardization

\- Outlier checking

\- Data validation



Preprocessing must be reproducible through scripts rather than manual row-by-row editing.





\## 10. Core Data Categories



\### Rainfall / Weather



\- Current rainfall

\- Historical rainfall

\- Rainfall intensity

\- Rainfall duration

\- Cumulative rainfall

\- Antecedent rainfall

\- Forecast rainfall

\- Temperature where useful

\- Other relevant weather variables



\### Terrain / Geography



\- Elevation

\- Slope

\- Low-lying areas

\- Water bodies

\- Drainage characteristics

\- Land use / land cover

\- Built-up density



\### Infrastructure



\- Roads

\- Drainage infrastructure

\- Hospitals

\- Schools

\- Emergency facilities

\- Critical infrastructure

\- Important public locations



\### Historical Events



\- Historical flooding

\- Historical waterlogging

\- Location

\- Severity where available

\- Duration where available

\- Date/time where available





\## 11. AI Risk Engine



The AI engine converts environmental and geographic information into flood/waterlogging risk intelligence.



Possible inputs:



\- Rainfall

\- Rainfall intensity

\- Rainfall duration

\- Forecast rainfall

\- Antecedent rainfall

\- Elevation

\- Slope

\- Drainage characteristics

\- Land use

\- Built-up density

\- Historical flooding/waterlogging



\### Required output



Risk Score:



0–100



Risk Level:



\- LOW

\- MODERATE

\- HIGH

\- VERY HIGH



Additional outputs where available:



\- Risk zone

\- Major contributing factors

\- Confidence / uncertainty

\- Relevant input values





\## 12. Scientific Integrity



The system MUST NOT claim perfect flood prediction.



If available historical labels are insufficient, the system must clearly distinguish between:



\- Flood forecasting

\- Flood susceptibility

\- Flood risk estimation

\- Scenario-based risk modelling



The model must not create false scientific certainty.



A simpler explainable model with defensible inputs is preferred over a complex model trained on weak or synthetic labels.





\## 13. Explainable AI



Every significant prediction should be explainable.



Example:



HIGH RISK



Primary factors:



\- High rainfall intensity

\- Low elevation

\- High built-up density

\- Drainage susceptibility

\- Historical waterlogging



The system should communicate WHY a zone received its risk level rather than only displaying a numerical score.





\## 14. Spatial Risk Visualization



The dashboard should provide an interactive map showing risk geographically.



Possible layers:



\- Flood risk

\- Rainfall

\- Elevation

\- Roads

\- Drainage

\- Hospitals

\- Schools

\- Critical infrastructure

\- Water bodies

\- Population / affected areas



Users should be able to toggle relevant layers.





\## 15. Infrastructure Impact Engine



The GIS / impact engine determines what may be affected by a predicted high-risk zone.



Example:



Risk Zone

&#x20;   ↓

Spatial intersection / proximity analysis

&#x20;   ↓

Affected assets



Possible outputs:



\- Roads affected

\- Hospitals affected

\- Schools affected

\- Critical infrastructure affected

\- Important locations affected

\- Population / area affected





\## 16. Impact Priority



Affected assets should be prioritized.



Example:



CRITICAL

HIGH

MEDIUM

LOW



Priority should consider factors such as:



\- Asset importance

\- Risk level

\- Proximity to risk zone

\- Accessibility

\- Population served

\- Criticality of infrastructure





\## 17. Recommendation Engine



The system should convert risk and impact information into actionable recommendations.



Examples:



\- Inspect drainage in high-risk areas

\- Prepare traffic diversion routes

\- Monitor access to critical facilities

\- Prepare emergency response resources

\- Issue precautionary alerts when appropriate

\- Prioritize specific infrastructure for inspection



Recommendations must be based on available system information.



The system must not present unsupported recommendations as authoritative emergency instructions.





\## 18. Scenario Simulation



The system must support controlled rainfall scenarios.



Example:



Rainfall:

180 mm



Duration:

6 hours



&#x20;       ↓



Run Simulation



&#x20;       ↓



Updated Risk



&#x20;       ↓



Updated Risk Zones



&#x20;       ↓



Updated Infrastructure Impact



&#x20;       ↓



Updated Recommendations





\### Example comparison



CURRENT:



Risk = 42

High-risk zones = 3



SIMULATED:



Risk = 81

High-risk zones = 11



The scenario system must clearly distinguish:



REAL / OBSERVED DATA



from



SIMULATED / ASSUMED DATA.





\## 19. Real + Historical + Simulated Data



The prototype may use three data modes:



\### Real



Current or live available information.



\### Historical



Previously observed information used for modelling and analysis.



\### Simulated



Controlled hypothetical scenarios used for demonstrations and stress testing.



The UI must clearly communicate which mode is being displayed.





\## 20. Patiala Ground-Truth Strategy



Long-term development should create a feedback loop:



Public / Historical Data

&#x20;       ↓

Initial Risk Model

&#x20;       ↓

Patiala Prediction

&#x20;       ↓

Real Rainfall Event

&#x20;       ↓

Ground Observation

&#x20;       ↓

Ground-Truth Dataset

&#x20;       ↓

Model Evaluation

&#x20;       ↓

Model Improvement



Ground-truth collection may include:



\- Waterlogging occurred / did not occur

\- Approximate severity

\- Approximate depth where safely observable

\- Duration

\- Location

\- Time

\- Photographic evidence where appropriate

\- Other relevant observations



This is a long-term improvement strategy and is NOT required to be fully implemented during the initial 3–4 day prototype.





\## 21. Climate Trends



Climate / historical rainfall trends may be included as a secondary analytical feature.



Possible metrics:



\- Extreme rainfall events

\- Rainfall intensity trends

\- Annual precipitation

\- Monsoon variability

\- Historical rainfall patterns



Climate trends are secondary to the core flood intelligence workflow.





\## 22. Dashboard



The dashboard should feel like a modern:



Municipal Emergency Management

\+

GIS Control Room

\+

Weather Intelligence Platform



It should prioritize clarity over decorative effects.



Primary interface areas may include:



\- Overview

\- Rainfall

\- Flood Risk

\- Risk Map

\- Infrastructure

\- Roads \& Drainage

\- Population Impact

\- Predictions

\- Scenario Simulation

\- Climate Trends

\- Recommendations

\- Analytics





\## 23. MVP Priority



\### MUST WORK



1\. Patiala map

2\. Rainfall / weather information

3\. Risk calculation

4\. Spatial risk visualization

5\. Infrastructure impact

6\. Recommendations

7\. Scenario simulation

8\. End-to-end integration



\### SHOULD WORK



9\. Explainable AI

10\. Historical rainfall analysis

11\. Multiple GIS layers

12\. Risk comparison



\### FUTURE / WOW FEATURES



13\. Advanced satellite integration

14\. Advanced precipitation fusion

15\. Automated alerts

16\. Advanced climate analytics

17\. 3D terrain / buildings

18\. Ground-truth collection system

19\. Automated model improvement





\## 24. Prototype Philosophy



The first prototype must prioritize:



\- Working system

\- End-to-end integration

\- Credible data

\- Explainable predictions

\- Strong visualization

\- Demonstrable decision support



Do NOT prioritize:



\- Perfect scientific accuracy

\- Complex models without sufficient data

\- Excessive features

\- Unnecessary architecture

\- Premature optimization



A smaller working system is better than many disconnected features.





\## 25. Module Ownership



| Module | Owner |

|---|---|

| Frontend / Dashboard | P1 |

| Backend / APIs | P2 |

| Database / Data Pipeline | P3 |

| AI / Risk Engine | P4 |

| GIS / Infrastructure / Impact | P5 |

| Integration / Architecture / Git | P6 |



P6 = Neekunj





\## 26. Module Responsibilities



\### P1 — Frontend



Owns:



\- Dashboard

\- Navigation

\- Maps

\- Charts

\- Risk cards

\- Rainfall display

\- Scenario UI

\- Recommendations display



Directory:



frontend/





\### P2 — Backend



Owns:



\- APIs

\- Request handling

\- Module communication

\- Data serving

\- AI integration

\- GIS integration



Directory:



backend/





\### P3 — Database / Data



Owns:



\- Data collection

\- Cleaning

\- Preprocessing

\- Database schema

\- Data storage

\- Processed datasets



Directories:



database/

data/raw/

data/processed/





\### P4 — AI



Owns:



\- Feature engineering for risk model

\- Model training

\- Risk scoring

\- Risk classification

\- Prediction output

\- Explainability



Directory:



ai-engine/





\### P5 — GIS / Infrastructure



Owns:



\- Geographic analysis

\- Risk-zone spatial operations

\- Roads

\- Drainage

\- Hospitals

\- Schools

\- Critical infrastructure

\- Impact analysis



Directory:



gis/





\### P6 — Integration / Architecture



Owns:



\- System architecture

\- Contracts

\- Git integration

\- Branch management

\- Cross-module testing

\- Integration

\- Final system quality

\- Final demonstration



P6 is the final integration authority.





\## 27. Module Independence



Each module must remain independently usable.



Modules communicate through clearly defined inputs and outputs.



A module must not directly modify another person's module without coordination.





\## 28. AI Coding Agent Rules



AI coding agents must follow the same ownership boundaries as humans.



An agent MUST:



\- Work only inside its assigned module

\- Respect the system contract

\- Preserve existing architecture

\- Avoid unnecessary refactoring

\- Write tests where appropriate

\- Explain major changes

\- Stop when its assigned task is complete



An agent MUST NOT:



\- Rewrite the entire project

\- Modify unrelated modules

\- Delete another person's work

\- Change architecture without approval

\- Perform broad cleanup

\- Install unnecessary dependencies

\- Expand geographic scope beyond Patiala

\- Add new major features without authorization





\## 29. Integration Contracts



Every module must document:



\### INPUT



What it receives.



\### PROCESS



What it does.



\### OUTPUT



What it provides.



Example:



AI Engine



INPUT:

Rainfall

Terrain

Drainage

Historical data



OUTPUT:

Risk score

Risk level

Risk factors

Risk zones





Backend



INPUT:

Data + AI + GIS outputs



OUTPUT:

Frontend API responses





Frontend



INPUT:

Backend responses



OUTPUT:

Human-readable dashboard.





\## 30. Geographic Expansion Rule



Any expansion beyond Patiala requires explicit approval from P6.



Expansion must be treated as a deliberate project decision, not an automatic feature.



Before expansion, the team must review:



\- Data availability

\- Model generalization

\- Geographic differences

\- Infrastructure differences

\- Validation requirements

\- Database design

\- API design

\- UI implications

\- Computational requirements



Until approval:



PATIALA ONLY.





\## 31. Git Rules



Nobody works directly on main.



Suggested branches:



frontend

backend

database

ai-engine

gis



Basic workflow:



Work

&#x20; ↓

Commit

&#x20; ↓

Push

&#x20; ↓

Review

&#x20; ↓

Merge

&#x20; ↓

Pull latest main



P6 controls integration and merging.





\## 32. Definition of Done



A feature is not considered complete merely because code exists.



A feature is complete when:



\- It works

\- It has been tested

\- Its input/output is understood

\- It does not break another module

\- It respects geographic scope

\- It respects ownership boundaries

\- It can be integrated into the main system





\## 33. Final Product Principle



We are NOT building:



"A weather app."



We are NOT building:



"An AI that claims to perfectly predict floods."



We are building:



An AI-powered urban flood intelligence and decision-support platform that converts rainfall, geographic, drainage, infrastructure, and historical information into predictive risk intelligence, spatial impact assessment, scenario analysis, explanations, and actionable recommendations.



Current deployment scope:



PATIALA, PUNJAB, INDIA.



Future expansion:



ONLY WHEN EXPLICITLY AUTHORIZED.


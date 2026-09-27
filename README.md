# analystlab-africa-internship
Weekly project submissions for the Analystlab Africa Data Analytics Internship Programme

## Week 4 — HealthConnect Experience Lab

From Week 4 onwards, the internship moves into a shared multi-track project: the HealthConnect Experience Lab, focused on improving patient appointment attendance using data and AI.

Week 4 deliverable (Data Analytics track): an Initial Analysis Document covering dataset overview, data quality assessment, key business questions, proposed KPIs, and an initial analysis approach for the HealthConnect appointment dataset.

See [Week-4-healthconnect-analysis](./Week-4-healthconnect-analysis) for the full document.

## Week 5 — HealthConnect Solution Development

Week 5 moved the project from planning into practical analysis. Calculated and interpreted 5 KPIs from the HealthConnect appointment dataset, produced supporting charts, and derived 5 business insights on appointment no-shows.

Key finding: booking lead time and prior no-show history are the strongest predictors of no-shows in the dataset.

See [Week-5-healthconnect-analysis](./Week-5-healthconnect-analysis) for the full report.


## Week 6 — HealthConnect Advanced Analytics & Decision Support

Validated the two strongest Week 5 findings (booking lead time and prior no-show history) using statistical significance testing, and found they compound: patients with both risk factors have a 58.3% no-show rate vs 18.4% for the lowest-risk group. Built and validated a composite risk score, and produced a structured handoff file for the Data Science track as this week's required cross-track integration.

See [Week-6-healthconnect-analysis](./Week-6-healthconnect-analysis) for the full report and handoff file.

## Week 7 — HealthConnect Analytics Testing & Refinement

Re-validated Week 6's KPIs independently (all matched). Found the 0-5 composite risk score broke down in 4 of 13 patient subgroups due to small sample sizes, and refined it into a validated 3-tier Low/Medium/High band that held up across all 13. As this week's HC-POD cross-track testing activity, found and fixed a real bug in the Data Science handoff file (a missing-value labeling issue that silently reappeared on reload).

See [Week-7-healthconnect-analysis](./Week-7-healthconnect-analysis) for the full report.


## Week 8 — HealthConnect Final Integration, Presentation & Project Showcase

Final week of the HealthConnect Experience Lab. Deliverables:
- Finalized all validated KPIs and the 3-tier no-show risk band (Low 22.8% / Medium 48.3% / High 63.7%)
- Documented two HC-POD integration activities with Data Science: the corrected risk-score handoff file (v2), and a direct cross-track feature validation exchange
- Identified a new compound-risk finding: patients with 2+ prior no-shows and 25.8km+ distance to clinic have an 80.0% no-show rate
- Produced the Final Analytics & Decision Support Report, HC-POD integration record, presentation slide summary, and individual video script
- Files: `HealthConnect_Week8_Final_Package_Omolade.pdf`, `HealthConnect_RiskScore_Handoff_for_DataScience_v2.csv`

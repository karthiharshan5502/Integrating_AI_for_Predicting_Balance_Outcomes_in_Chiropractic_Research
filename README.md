# Integrating_AI_for_Predicting_Balance_Outcomes_in_Chiropractic_Research
Relationship between vertebral subluxation and balance indicators

This project uses AI and data science to explore how chiropractic adjustments affect balance and stress in patients, analyzing real clinical data from ~200 participants over 12–16 weeks.

Project Overview
The study investigates vertebral subluxation (spinal dysfunction) and its links to balance (postural sway, gait like step velocity/symmetry) and stress markers. Participants were split into active (receiving chiropractic care) and passive (control) groups, including adults and children. Data was collected at baseline (week 0), mid-point (week 6), end (week 12), and follow-up (week 16). Key goal: See if care improves balance and if subluxation scores predict outcomes.

Data Sources
Balance Data: IMU sensors via G&B Mobile App on smartphones—measures postural sway (mediolateral ML, anteroposterior AP, resultant R) on firm/compliant surfaces, eyes open/closed.

Gait Data: Walking metrics like step length/time, velocity, symmetry during head-forward/turned trials.
​

Subluxation Data: Clinician-scored (1=mild to 3=severe) per spinal region from Excel files, weighted (e.g., C1-C2 x3 for importance).
​

Methodology & Data Science Approach
Preprocessing: Merged active/passive datasets, extracted/weighted subluxation scores, cleaned outliers/duplicates, standardized dates, created time-point scores (baseline/mid/post) and slopes (rate of change).

Exploratory Analysis: Plots showed active groups had declining subluxation scores vs. stable/flat in passive; children improved more.

Modeling:

Linear Mixed Models (LMM) for intervention effects (handles repeated measures).
​

ML for prediction: Random Forest, Gradient Boosting (best, R² up to 0.88), SVR, LSTM (good fit but higher error).

Validation: RMSE, R², cross-validation; feature importance showed gait/step velocity as top predictors, subluxation slopes secondary.​

Key Findings
Objective 1 (Care Impact): Children in active group saw big gains—e.g., 9.52–10.14% step velocity increase, 5–10% gait symmetry boost. Adults had mixed/smaller changes; postural sway sometimes worsened on unstable surfaces.

Objective 2 (Prediction): Subluxation predicts balance modestly (esp. when gait data limited); models accurate (R² 0.6–0.93), with step velocity/length most influential.

Trends: Active groups improved more; kids respond better than adults.
​

Limitations & Next Steps
Challenges: Dropouts (COVID), infrequent balance checks, data gaps. Future: More frequent data, causal models, add workload factors.

This repo contains code/notebooks for preprocessing, EDA, LMM/ML models—clone, install Python libs (pandas, scikit-learn, etc.), and run Jupyter files to reproduce.

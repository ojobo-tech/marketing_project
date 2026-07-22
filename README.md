# AI Campaign Performance Scoring Decision-Support System

A modular AI decision-support project that scores marketing campaigns by likelihood of strong performance, explains why a campaign was ranked a certain way, and helps teams decide where to focus effort and budget.

## Project goal

Build a practical campaign-scoring system that turns raw campaign data into:
- a priority score
- a ranked list of campaigns
- explanation reasons
- recommended next actions
- a simple client-facing dashboard

## Business problem

Marketing teams often have campaign data but no clear way to answer:
- which campaigns are likely to perform well,
- which audience and channel combinations are strongest,
- where spend is being wasted,
- and what action to take next.

This project solves that by creating an end-to-end scoring and decision-support workflow.

## Dataset

The project uses a marketing campaign performance dataset with roughly 200,000 rows across two years.

Core columns include:
- Company
- Campaign_Type
- Target_Audience
- Duration
- Channels_Used
- Conversion_Rate
- Acquisition_Cost
- ROI
- Location
- Language
- Clicks
- Impressions
- Engagement_Score
- Customer_Segment
- Date

## Scope

This is a 5-day MVP project focused on:
- data understanding
- feature engineering
- model training and validation
- explainability
- Streamlit dashboard delivery

## Target definition

The primary target will be a binary label such as:
- high performing campaign = 1
- not high performing = 0

This will be derived from conversion performance.

## Repository structure

- `data/` raw and processed datasets
- `notebooks/` analysis and modeling notebooks
- `src/` reusable pipeline code
- `models/` saved model artifacts
- `app/` Streamlit dashboard
- `reports/` charts, outputs, and exported results

## Workflow

1. Load and inspect the campaign data
2. Clean and standardize fields
3. Engineer performance, efficiency, and time-based features
4. Train and compare models
5. Add explainability and business actions
6. Deploy a Streamlit dashboard

## Deliverables

- cleaned dataset
- engineered features
- trained model
- explainability outputs
- ranked campaign scores
- Streamlit dashboard

## Next steps

1. Build the data understanding notebook
2. Define the target and final feature set
3. Train baseline and stronger models
4. Add XAI and scoring logic
5. Connect everything to Streamlit
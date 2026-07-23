# AI Campaign Performance Scoring Decision-Support System

This project builds an explainable campaign performance scoring system to help marketing teams prioritize campaigns, understand which campaigns are likely to perform well, and decide where to allocate effort and budget. The goal is not only prediction, but decision support.

It is a modular AI decision-support project that scores marketing campaigns by likelihood of strong performance, explains why a campaign was ranked a certain way, and helps teams decide where to focus effort and budget.

## Project goal

Turn raw marketing campaign data into:

- a priority score
- a ranked list of campaigns
- explanation reasons
- recommended next actions
- a simple client-facing dashboard

## Business problem

Marketing teams often have campaign data but no clear way to answer:

- which campaigns are likely to perform well
- which audience and channel combinations are strongest
- where spend is being wasted
- what action to take next

This project addresses that need by creating an end-to-end scoring and decision-support workflow.

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

This is a  project focused on:

- data understanding
- feature engineering
- model training and validation
- explainability

## Target definition

The primary target is a binary label that identifies whether a campaign is high performing. This makes the project suitable for campaign prioritization, ranking, and decision support.

- `high_performing_campaign = 1` if `Conversion_Rate` is in the top quartile of campaigns
- `high_performing_campaign = 0` otherwise

This target is derived from conversion performance.

## Responsible AI approach

This project is developed with a Responsible AI mindset. The goal is not only to predict campaign performance, but to do so in a way that is explainable, business-oriented, and mindful of how model outputs may influence marketing decisions.

The model is evaluated not only on predictive performance, but also on interpretability, ranking usefulness, and whether the outputs can be understood and reviewed by a business user. Because this is a decision-support tool, the explanations and limitations matter as much as the score itself.

## Key project outputs

- cleaned dataset
- engineered features
- trained model
- explainability outputs
- ranked campaign scores
- Streamlit dashboard

## Results and limitations

The project demonstrates a complete campaign-scoring workflow from raw data to feature engineering, model training, validation, and explainability. The analysis also shows an important limitation: the current feature set does not produce strong predictive separation between high-performing and non-high-performing campaigns.

Across the modeling experiments:
- logistic regression remained close to random ranking performance
- random forest did not materially improve ranking quality
- gradient boosting also stayed near random
- time-aware validation confirmed that this was not just a random-split issue

The most important finding is that the raw campaign variables in this dataset have very weak standalone signal for strong classification at the current target definition. Numeric features showed almost no linear association with the target, and categorical features showed only very small differences in target rate across categories.

This is still a valuable result. It means the project is honest about what the data can and cannot support. The value of the work is not only in the final score, but also in the disciplined workflow, feature audit, validation strategy, and business interpretation of weak signal.

## Key findings

- The dataset is structurally clean and suitable for analysis.
- The target is moderately imbalanced, which makes ranking metrics more useful than accuracy alone.
- Single-feature business variables do not strongly separate campaign performance.
- Engineered efficiency and time features improve interpretability, but not enough to create strong predictive lift.
- Time-aware validation confirms that the weak signal is persistent over time.
- The strongest project outcome is the decision-support workflow, not a high-separation classifier.

## Responsible AI considerations

This project was developed with a Responsible AI mindset.

That means:
- outcome variables such as `Conversion_Rate` and `ROI` were treated carefully to avoid leakage
- the model was evaluated using interpretable metrics and ranking-based metrics
- the analysis avoided overclaiming causality from descriptive patterns
- the limitations of the data and model were documented explicitly
- the final output is positioned as decision support, not automated business truth

The project is intended to help humans review, prioritize, and interpret campaigns more effectively, not to replace business judgment.

## Future Enhancements

- enrich the dataset with historical and aggregate campaign features
- test segment-level or company-level baselines
- refine the target definition
- improve interaction features
- iterate on explainability



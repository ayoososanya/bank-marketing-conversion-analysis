# Beyond the Average Customer: Predicting Conversion in Bank Marketing

## Overview
This project analyses a real-world bank marketing dataset to understand what 
drives customer conversion. Rather than stopping at descriptive statistics, 
we combine demographic profiling, financial behaviour analysis, statistical 
hypothesis testing, and machine learning to build a complete picture of who 
converts and why. The analysis ends with five specific, actionable recommendations 
for a Strategy and Marketing team.

## Business Question
What customer profiles and behaviours predict conversion to a term deposit product, 
and what does that tell us about how a fintech should prioritise its outreach 
and product strategy?

## Tools & Technologies
- **Python** - core analysis and modelling
- **Pandas** - data cleaning and manipulation
- **NumPy** - numerical operations
- **Matplotlib** - data visualisation
- **SciPy** - statistical hypothesis testing (Mann-Whitney U test)
- **Scikit-learn** - logistic regression modelling, train/test split, 
  model evaluation

## Dataset
UCI Machine Learning Repository: Bank Marketing Dataset
- 45,211 rows, 17 columns (raw)
- 30,905 rows after cleaning
- Source: Real Portuguese bank direct marketing campaign data
- Target variable: whether a customer subscribed to a term deposit (yes/no)

## Project Structure

### Act 1: Who Are Our Customers?
Demographic analysis covering age, job type, education level, and marital status. 
We identify that the customer base skews toward 31 to 50 year olds in management 
and technical roles, but surface two underexplored segments: 18 to 30 year olds 
and customers aged 65 and over.

### Act 2: What Is Their Financial Picture?
Analysis of account balance, loan status, and default history. We find that the 
typical customer holds a median balance of just £448, a figure heavily distorted 
by a small number of high balance outliers. We define our ideal customer profile, 
Wise Wendy, based on balance range, debt status, and financial behaviour.

### Act 3: What Predicts Conversion?
Statistical hypothesis testing confirms that balance, loan status, and default 
history are all genuine predictors of conversion, not random variation. A logistic 
regression model then identifies the most influential features simultaneously, 
revealing that previous campaign success, campaign timing, and age group are the 
strongest drivers of conversion likelihood.

## Key Findings

1. **Previous campaign success is the strongest predictor of conversion**, nearly 
   three times more influential than any other factor. Customers who converted 
   before should be the first segment targeted in any future campaign.

2. **Campaign timing matters significantly.** March, June, September and October 
   produce the strongest conversion rates, aligning with periods of financial 
   stability and end of year reflection. August and November are the weakest months, 
   coinciding with holiday spending and pre-Christmas financial pressure.

3. **The business is targeting the wrong age groups.** The 65+ segment converts 
   at 43.1% and the 18 to 30 segment at 20%, yet the majority of outreach targets 
   the 31 to 50 group which converts at only 11 to 13%.

4. **Financial commitments are a strong negative signal.** Customers with personal 
   loans convert at half the rate of those without. Customers with housing loans 
   are among the weakest performers in the model.

5. **Our ideal customer is Wise Wendy.** Aged 25 to 40, balance between £1,500 
   and £3,500, no existing loans, never defaulted, works in a stable professional 
   role. Every campaign should be built around her profile first.

## Limitations

- **Contact method data was missing for 29% of customers** and those rows were 
  dropped during cleaning. If customers without logged contact methods differ 
  systematically from those with complete records, our analysis may underrepresent 
  certain segments.

- **The dataset reflects one campaign from one institution.** Findings may not 
  generalise directly to a digital-first bank like Monzo or Revolut, whose customer 
  demographics and behaviours may differ from a traditional Portuguese bank.

- **The model predicts conversion to a term deposit specifically**, not overall 
  customer engagement or churn. These are related but distinct concepts and should 
  not be conflated.

- **Class imbalance required a balanced weighting approach.** Our final model 
  achieves a recall of 59% for converters, meaning it still misses approximately 
  41% of customers who would have said yes. Further improvement could be achieved 
  with more advanced techniques such as SMOTE or gradient boosting.

## How to Run

1. Clone the repository
2. Download the dataset from the UCI Machine Learning Repository
3. Place `bank-full.csv` in the project root directory
4. Open `bank_marketing_conversion_analysis.ipynb`
5. Run all cells in order

## Author
Ayoola Ososanya
[LinkedIn](https://linkedin.com/in/ayoola-ososanya)

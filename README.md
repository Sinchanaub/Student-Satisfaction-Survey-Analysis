# Student Satisfaction Survey Analysis

A Python data analysis of a student satisfaction survey: cleaning the data, scoring ratings, and running TextBlob sentiment analysis, with visualizations and recommendations.

## Overview

| | |
|---|---|
| Dataset | `Student_Satisfaction_Survey.csv` (580 records, 12 columns) |
| Content | Survey questions, weighted rating counts (1-5), average scores, course name |
| Tools | Python · pandas · matplotlib · seaborn · TextBlob |

## Workflow

### 1. Load the data
Imported the libraries and loaded the CSV into a pandas DataFrame (using `latin1` encoding).

![Loading data](load%20data.png)

### 2. Clean the data and extract numeric scores
Checked for missing values (none found; 580 rows kept). The `Average/Percentage` column was stored as text like `3.00 / 60.00`, so the numeric score was extracted and converted to float.

![Cleaning and extracting](clean%20and%20extract.png)

### 3. Rating analysis
The average satisfaction score is **3.84 out of 5**. Scores were grouped into low (up to 2.5), medium (2.5-3.5) and high (3.5-5), and most records fall in the **high** group.

![Satisfaction levels](satisfaction%20level.png)

### 4. Sentiment analysis (NLP)
TextBlob polarity scores were computed on the survey text and labeled Positive, Neutral or Negative. Results: **Neutral 319, Positive 203, Negative 58** (about 55%, 35% and 10%).

![Sentiment distribution](sentiment.png)

### 5. Sentiment distribution as a pie chart

![Sentiment pie chart](pie.png)

## Key findings

- Most records show medium to high satisfaction (average 3.84 / 5).
- Neutral sentiment dominates, followed by positive. Negative sentiment is a small share.

![Observations](observe.png)

## Recommendations

- Add open-ended feedback questions to capture detailed opinions.
- Increase interactive sessions to boost engagement.
- Collect feedback regularly to track improvement over time.

## Limitations

- The sentiment scores are calculated on the **survey question text**, not on students' written responses, so they reflect how the questions are worded rather than how students feel. The rating analysis (average score) is the more reliable measure of satisfaction here.
- Each record is a survey item aggregate, so counts show "records", not individual students.
- Next step: apply sentiment analysis to open-ended student comments once such data is available.

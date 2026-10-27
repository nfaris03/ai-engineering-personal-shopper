# Topic 2 — Evaluation Criteria

## 1. Evaluation Overview

The AI-Powered Personal Shopper will be evaluated based on product search, product comparison, sentiment classification, ranking quality, response time, and reliability. Testing will initially use prepared data and controlled test scenarios.

## 2. Evaluation Criteria

### EC1 — Product Search

- **Objective:** O1 — Develop a web application for product comparison.
- **Requirement:** FR1 — Product search.
- **Evaluation Method:** Test at least 20 product queries against the available dataset.
- **Metric:** Successful search rate.
- **Proposed Threshold:** At least 95%.
- **Expected Outcome:** Users can find supported products through the application.

### EC2 — Product Comparison

- **Objective:** O1 — Compare product information.
- **Requirements:** FR2 and FR3 — Product details and comparison.
- **Evaluation Method:** Check at least 20 product records against the source data.
- **Metric:** Attribute correctness.
- **Proposed Threshold:** At least 95%.
- **Expected Outcome:** Displayed product details match the available source information.

### EC3 — Sentiment Analysis

- **Objective:** O2 — Apply NLP-based sentiment analysis.
- **Requirement:** FR4 — Review sentiment analysis.
- **Evaluation Method:** Test predictions on labelled reviews that were not used for training.
- **Metric:** Macro-F1 score.
- **Proposed Threshold:** At least 0.75.
- **Expected Outcome:** The model classifies customer review sentiment with acceptable performance.

### EC4 — Product Ranking

- **Objective:** O2 — Rank products based on user preferences.
- **Requirement:** FR5 — Product ranking.
- **Evaluation Method:** Evaluate at least 20 test scenarios using predefined relevance judgements.
- **Metric:** Precision@5.
- **Proposed Threshold:** At least 0.70.
- **Expected Outcome:** Relevant products appear among the top five results.

### EC5 — Response Time

- **Objective:** O3 — Evaluate system performance.
- **Requirement:** NFR1 — Performance.
- **Evaluation Method:** Measure the response time of at least 50 queries under the same test conditions.
- **Metric:** 90th-percentile response time (p90).
- **Proposed Threshold:** No more than 5 seconds for preloaded data.
- **Expected Outcome:** The application returns results within a reasonable time.

### EC6 — System Reliability

- **Requirement:** NFR4 — Reliability.
- **Evaluation Method:** Run at least 50 valid queries and record successful responses.
- **Metric:** Successful query rate.
- **Proposed Threshold:** At least 95%.
- **Expected Outcome:** Most supported queries complete without system errors.

### EC7 — Source Transparency

- **Requirement:** RAI1 — Source transparency.
- **Evaluation Method:** Inspect product results for source details and timestamps where available.
- **Metric:** Percentage of applicable results displaying source and timestamp information.
- **Proposed Threshold:** 100%.
- **Expected Outcome:** Users can identify where product information came from and how recent it is when this information is available.

### EC8 — Ranking Transparency

- **Requirement:** RAI3 — Ranking transparency.
- **Evaluation Method:** Inspect ranking results to confirm that the main ranking criteria are displayed.
- **Metric:** Percentage of results showing ranking criteria.
- **Proposed Threshold:** 100%.
- **Expected Outcome:** Users can understand the main factors influencing product rankings.

## 3. Evaluation Procedure

1. Prepare the product dataset and labelled review test set.
2. Separate training and test data where model training is required.
3. Run the defined test queries and record the results.
4. Calculate the relevant metrics and compare them with the proposed thresholds.
5. Document failed tests, limitations, and possible improvements.

## 4. Success Criteria

The project will be considered successful if it demonstrates product search and comparison, produces measurable sentiment and ranking results, and reports its performance transparently.

The proposed thresholds are targets, not achieved results. Actual performance will be measured during testing.

## 5. Reflection

A working application does not necessarily produce accurate recommendations. Separate test data, predefined relevance judgements, and recorded response times will help evaluate performance objectively. Product data may also be incomplete or outdated, and sentiment models may misinterpret sarcasm or context. These limitations will be considered when interpreting the results.

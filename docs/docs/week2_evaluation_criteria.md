\# Topic 2 — Evaluation Criteria



\## 1. Evaluation Overview



The AI-Powered Personal Shopper will be evaluated based on product search, product comparison, sentiment classification, ranking quality, response time, and reliability. Testing will initially use prepared data and controlled test scenarios.



\## 2. Evaluation Criteria



| ID | Objective / Requirement | Evaluation Method | Metric | Proposed Threshold | Expected Outcome |

|---|---|---|---|---|---|

| EC1 | O1 / FR1: Product search | Test at least 20 product queries against the available dataset. | Successful search rate | ≥ 95% | Users can find supported products. |

| EC2 | O1 / FR2–FR3: Product comparison | Check at least 20 product records against source data. | Attribute correctness | ≥ 95% | Displayed product details match the available data. |

| EC3 | O2 / FR4: Sentiment analysis | Test predictions on labelled reviews not used for training. | Macro-F1 score | ≥ 0.75 target | The model classifies review sentiment reliably. |

| EC4 | O2 / FR5: Product ranking | Evaluate at least 20 scenarios using predefined relevance judgements. | Precision@5 | ≥ 0.70 target | Relevant products appear among the top five results. |

| EC5 | O3 / NFR1: Response time | Measure at least 50 queries under the same conditions. | 90th-percentile response time (p90) | ≤ 5 seconds for preloaded data | Results are returned within the target time. |

| EC6 | NFR4: Reliability | Run at least 50 valid queries and record successful responses. | Successful query rate | ≥ 95% | Most supported queries complete without errors. |

| EC7 | RAI1: Source transparency | Inspect results for source details and timestamps where available. | Results with source and timestamp when available | 100% | Users can identify data sources and freshness. |

| EC8 | RAI3: Ranking transparency | Inspect ranking results for displayed criteria. | Results with ranking criteria shown | 100% | Users can understand the main ranking factors. |



\## 3. Evaluation Procedure



1\. Prepare the product dataset and labelled review test set.

2\. Separate training and test data where model training is required.

3\. Run the test queries and record the outputs.

4\. Calculate the relevant metrics and compare them with the proposed thresholds.

5\. Document failed tests, limitations, and possible improvements.



\## 4. Success Criteria



The project will be considered successful if it demonstrates product search and comparison, produces measurable sentiment and ranking results, and reports its performance transparently. Thresholds are targets and must be verified through actual testing.



\## 5. Reflection



A working application does not necessarily produce accurate recommendations. Separate test data, predefined relevance judgements, and recorded response times will help evaluate performance objectively. Results will be reported based on measurements rather than assumptions.


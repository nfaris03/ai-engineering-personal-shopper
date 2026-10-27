\# Topic 2 — Project Framing and Requirements



\## 0. Project Framing and Application Scope



\### Project Name

AI-Powered Personal Shopper for Online Shopping Platforms



\### Problem Statement

Online shoppers often need to compare product prices, specifications, and customer reviews across different e-commerce platforms. This process can be time-consuming and makes it difficult to identify products that offer the best value. This project proposes an AI-powered personal shopper that compares available product information, analyses customer review sentiment, and ranks products according to user preferences.



\### Problem Evidence

\- E-commerce product information and customer reviews can be spread across multiple listings and platforms.

\- The UCSD Amazon Product Reviews and Metadata dataset provides product and review data that can support initial experimentation.

\- Access to live product information depends on the availability and permission of each platform's API or other approved data source.



\### Existing Approaches

\- \*\*Manual product comparison:\*\* Users compare prices, specifications, and reviews themselves, which can take time.

\- \*\*Platform recommendation systems:\*\* Individual platforms may recommend products, but users may still need to compare products across different platforms.

\- \*\*Sentiment analysis:\*\* NLP models can classify review sentiment, but sentiment alone does not determine whether a product is the best choice for an individual user.



\### Project / Engineering Gap

A lightweight system is needed to combine product comparison, review sentiment analysis, and preference-based ranking in one interface. The system will aim to help users make more informed purchasing decisions without assuming unrestricted access to e-commerce platform data.



\### Objectives

\- \*\*O1:\*\* Develop a web application that displays and compares available product information.

\- \*\*O2:\*\* Apply NLP-based sentiment analysis and preference-based ranking to support product recommendations.

\- \*\*O3:\*\* Evaluate the system using product ranking quality, sentiment classification performance, and response time.



\### Intended Users

Online shoppers who want to compare products and identify suitable options based on price, product features, and customer feedback.



\### Supported Tasks

\- Search for products within the supported dataset or approved data sources.

\- Compare available prices and product specifications.

\- View customer review sentiment summaries.

\- Rank products according to selected preferences.



\### Information / Knowledge Domain

E-commerce product information, product specifications, customer reviews, NLP sentiment analysis, and product ranking.



\### Operating Context

The system will be developed as a student project using Python and a web interface. Initial testing may use a prepared dataset. Live platform integration will depend on verified API access, permissions, and technical feasibility.



\### Important Constraints

\- Product coverage depends on the available dataset and permitted sources.

\- Product prices and availability may change over time.

\- Sentiment analysis may misinterpret sarcasm, context, or ambiguous reviews.

\- The project has limited development time and computing resources.

\- No unrestricted access to Shopee or Lazada data is assumed.



\### Explicit Out-of-Scope Tasks

\- Purchasing products or processing payments.

\- Guaranteeing that a product is the cheapest across the entire internet.

\- Collecting data through methods that violate platform terms or access restrictions.

\- Providing financial guarantees or claiming that recommendations are always correct.



\### Evaluation Focus

The system will be evaluated through sentiment classification performance, product ranking quality, response time, successful query completion, and the clarity of product information presented to users.



\## 1. Functional Requirements



| ID | Requirement — System SHALL | Scope Boundary — System SHALL NOT |

|---|---|---|

| FR1 | Allow users to search for products in the supported data sources. | Claim to search every e-commerce platform. |

| FR2 | Display available product details, including price and specifications where available. | Invent missing product information. |

| FR3 | Compare products using available attributes. | Compare attributes that are unavailable or incompatible without indicating the limitation. |

| FR4 | Analyse customer reviews and produce sentiment results. | Treat predicted sentiment as guaranteed fact. |

| FR5 | Rank products using supported criteria and user preferences. | Claim recommendations are objectively best for every user. |

| FR6 | Display product information, sentiment summaries, and ranking results through a web interface. | Process purchases or payments. |



\## 2. Non-Functional Requirements



| ID | Quality Attribute | Requirement | Measurement Method | Metric | Proposed Threshold |

|---|---|---|---|---|---|

| NFR1 | Performance | Return results within a reasonable time. | Time at least 50 test queries using the same test environment. | 90th-percentile response time (p90) | ≤ 5 seconds for preloaded data |

| NFR2 | Sentiment quality | Classify customer review sentiment reliably. | Evaluate on a labelled test set not used for training. | Macro-F1 score | ≥ 0.75, if supported by the test data |

| NFR3 | Ranking quality | Place relevant products near the top of the results. | Evaluate at least 20 test scenarios with defined relevance judgements. | Precision@5 | ≥ 0.70, if supported by the evaluation set |

| NFR4 | Reliability | Handle valid supported searches without system errors. | Run at least 50 test queries and record successful responses. | Successful query rate | ≥ 95% |

| NFR5 | Maintainability | Allow supported data sources or ranking criteria to be updated without redesigning the entire application. | Test a configuration or criteria change. | Successful update test | At least one documented change completed without major redesign |



\## 3. Responsible AI Requirements



| ID | Risk | Requirement | Measurement Method | Metric | Proposed Threshold |

|---|---|---|---|---|---|

| RAI1 | Misleading information | Show available source information and data timestamps where possible. | Inspect displayed product results. | Results with source and timestamp when available | 100% |

| RAI2 | Incorrect sentiment | Present sentiment as a model prediction, not a confirmed fact about a product or reviewer. | Review interface labels and sample outputs. | Outputs with appropriate sentiment labels | 100% |

| RAI3 | Biased or unsuitable ranking | Explain the main criteria used to rank products. | Inspect ranking explanations for test scenarios. | Results with ranking criteria shown | 100% |

| RAI4 | Privacy | Avoid collecting unnecessary personal information; use preferences only for the intended recommendation task. | Inspect input fields and data handling. | Unnecessary personal data fields | 0 |



\### Reflection

The project combines product comparison with NLP-based review analysis to make shopping decisions easier. However, the quality of recommendations depends on the completeness and freshness of product data, while sentiment models may misinterpret sarcasm or context. The project will therefore use permitted data sources, clearly communicate limitations, and evaluate its performance before making claims about recommendation quality.


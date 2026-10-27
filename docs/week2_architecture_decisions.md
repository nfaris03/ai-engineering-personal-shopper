\# Topic 2 — Architecture Decisions



\## 1. Architecture Overview



The AI-Powered Personal Shopper uses a modular web application architecture. The web interface accepts product searches and user preferences. The backend coordinates product retrieval, comparison, NLP sentiment analysis, and product ranking before returning results to the user.



The first version will use prepared product data or approved APIs. Live integration with Shopee or Lazada will depend on verified access and platform permissions.



\## 2. Architecture Decisions



\### AD1 — Modular Backend



\*\*Decision:\*\* Use a Python backend with separate modules for product comparison, sentiment analysis, and product ranking.



\*\*Rationale:\*\* Each module has a different responsibility and can be tested or improved independently.



\*\*Alternatives considered:\*\*

\- A single block of code handling all operations.

\- Separate microservices for each component.



\*\*Trade-offs:\*\* A modular backend is easier to maintain than one large block of code while avoiding the deployment complexity of multiple microservices.



\### AD2 — Prepared Data Before Live Integration



\*\*Decision:\*\* Start with a prepared product and review dataset, then integrate external APIs if access and permissions are confirmed.



\*\*Rationale:\*\* Development and testing can continue without depending entirely on live e-commerce platforms.



\*\*Alternatives considered:\*\*

\- Depending on live Shopee and Lazada APIs from the beginning.

\- Collecting data through automated website scraping.



\*\*Trade-offs:\*\* Prepared data supports repeatable testing but may not reflect current prices. Live APIs may provide fresher information but depend on access permissions, rate limits, and available fields. Data collection must follow platform rules.



\### AD3 — Separate Sentiment Analysis from Ranking



\*\*Decision:\*\* Analyse review sentiment separately, then combine review insights with other available product attributes during ranking.



\*\*Rationale:\*\* Positive reviews alone do not guarantee that a product is affordable or suitable for a particular user.



\*\*Alternatives considered:\*\*

\- Ranking products using sentiment alone.

\- Ranking products using price alone.



\*\*Trade-offs:\*\* Combining criteria can better reflect user preferences but requires consistent product information and a clearly defined ranking method.



\## 3. Traceability Matrix



| Requirement ID | Related Component | Related Decision | Explanation |

|---|---|---|---|

| FR1 | Web Interface, Backend API | AD1, AD2 | Supports product searches using available data. |

| FR2–FR3 | Product Data Source, Comparison Module | AD1, AD2 | Compares available prices and specifications. |

| FR4 | NLP Sentiment Analysis | AD1, AD3 | Analyses review sentiment as a separate task. |

| FR5 | Ranking Engine | AD1, AD3 | Ranks products using available attributes and user preferences. |

| FR6 | Web Interface | AD1 | Displays product comparisons and recommendations. |

| NFR1, NFR4 | Backend API, Database / Cache | AD1, AD2 | Supports response-time and reliability testing. |

| NFR2, NFR3 | Sentiment Analysis, Ranking Engine | AD3 | Allows sentiment and ranking performance to be evaluated separately. |

| NFR5 | Backend Modules | AD1 | Supports updates without redesigning the whole system. |

| RAI1, RAI2 | Data Source, Sentiment Analysis | AD2, AD3 | Supports source transparency and responsible presentation of sentiment. |

| RAI3, RAI4 | Ranking Engine, Web Interface | AD3 | Supports ranking explanations and minimises unnecessary personal data collection. |



\## 4. Reflection



The modular architecture allows each main function to be developed and evaluated independently. Starting with prepared data reduces dependence on external platforms, while separating sentiment analysis from ranking makes the system easier to test.



The main trade-off is between data freshness and development feasibility. The first version will prioritise core functionality, transparent limitations, and measurable evaluation before expanding its data sources.


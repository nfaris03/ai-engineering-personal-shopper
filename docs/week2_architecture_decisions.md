# Topic 2 — V1 Architecture Decisions

## 1. Architecture Overview

The AI-Powered Personal Shopper will use a modular web application architecture. The web interface accepts product searches and user preferences. The backend coordinates product retrieval, comparison, sentiment analysis, and product ranking before returning results.

The first version will use prepared product data or approved APIs. Live integration with Shopee or Lazada will depend on verified access and platform permissions.

### Main Components

**Web Interface**
- Accept product searches and preferences.
- Display product comparisons and recommendations.
- Show sentiment summaries and available source information.

**Backend API**
- Receive and validate user requests.
- Coordinate processing between modules.
- Return results to the interface.

**Product Data Source**
- Provide available product details, prices, specifications, and reviews.
- Use prepared datasets or permitted APIs.

**Product Matching and Comparison**
- Match comparable products.
- Compare available prices and specifications.

**NLP Sentiment Analysis**
- Process customer review text.
- Estimate review sentiment.
- Summarise review patterns.

**Ranking Engine**
- Apply user preferences.
- Combine available product attributes and review insights.
- Generate ranked results.

**Database / Cache**
- Store prepared product data where needed.
- Cache repeated queries where appropriate.

## 2. Architecture Decisions

### AD1 — Use a Modular Backend

**Decision:** Use a Python backend with separate modules for product comparison, sentiment analysis, and product ranking.

**Rationale:** Each module has a different responsibility and can be tested or improved independently.

**Alternatives considered:**
- One block of code handling all operations.
- Separate microservices for every component.

**Trade-offs:** A modular backend is easier to maintain than one large block of code without introducing the deployment complexity of multiple microservices.

### AD2 — Start with Prepared Data and Approved Sources

**Decision:** Start with prepared product and review data, then integrate external APIs if access and permissions are confirmed.

**Rationale:** Development and testing can continue without depending entirely on live platform access.

**Alternatives considered:**
- Depending on live Shopee and Lazada APIs from the beginning.
- Automated website scraping.

**Trade-offs:** Prepared data supports repeatable testing but may not reflect current prices. APIs may provide fresher information but depend on access permissions, rate limits, and available fields. Data collection must follow platform rules.

### AD3 — Separate Sentiment Analysis from Ranking

**Decision:** Analyse review sentiment separately, then combine review insights with other product attributes during ranking.

**Rationale:** Positive reviews alone do not guarantee that a product is affordable or suitable for a particular user.

**Alternatives considered:**
- Ranking products using sentiment alone.
- Ranking products using price alone.

**Trade-offs:** Combining criteria can better reflect user preferences but requires consistent product information and a clearly defined ranking method.

## 3. Traceability

### FR1 — Product Search
- **Related components:** Web Interface and Backend API.
- **Related decisions:** AD1 and AD2.
- **Explanation:** Search uses supported data sources and modular processing.

### FR2 and FR3 — Product Information and Comparison
- **Related components:** Product Data Source and Product Matching and Comparison.
- **Related decisions:** AD1 and AD2.
- **Explanation:** Product comparisons depend on the availability and consistency of source data.

### FR4 — Sentiment Analysis
- **Related component:** NLP Sentiment Analysis.
- **Related decisions:** AD1 and AD3.
- **Explanation:** Sentiment is handled as a separate, testable component.

### FR5 — Product Ranking
- **Related component:** Ranking Engine.
- **Related decisions:** AD1 and AD3.
- **Explanation:** Ranking combines available product attributes with user preferences.

### FR6 — Results Display
- **Related components:** Web Interface and Backend API.
- **Related decisions:** AD1 and AD2.
- **Explanation:** Results show product comparisons, ranking information, and available source details.

### NFR1 and NFR4 — Performance and Reliability
- **Related components:** Backend API and Database / Cache.
- **Related decisions:** AD1 and AD2.
- **Explanation:** Modular processing and optional caching can support performance and reliability testing.

### NFR2 and NFR3 — Sentiment and Ranking Quality
- **Related components:** NLP Sentiment Analysis and Ranking Engine.
- **Related decision:** AD3.
- **Explanation:** Sentiment classification and product ranking are evaluated separately.

### NFR5 — Maintainability
- **Related component:** Backend modules.
- **Related decision:** AD1.
- **Explanation:** Individual modules can be updated without redesigning the entire system.

### RAI1 and RAI2 — Source Transparency and Sentiment
- **Related components:** Product Data Source, NLP Sentiment Analysis, and Web Interface.
- **Related decisions:** AD2 and AD3.
- **Explanation:** Product sources and estimated sentiment must be communicated clearly.

### RAI3 and RAI4 — Ranking Transparency and Privacy
- **Related components:** Ranking Engine, Web Interface, and data handling.
- **Related decisions:** AD2 and AD3.
- **Explanation:** Ranking criteria should be explained, and unnecessary personal information should not be collected.

## 4. Reflection

The modular architecture allows each main function to be developed and evaluated independently. Starting with prepared data reduces dependence on external platforms, while separating sentiment analysis from ranking makes the system easier to test.

The main trade-off is between data freshness and development feasibility. The first version will prioritise core functionality, transparent limitations, and measurable evaluation before expanding its data sources.

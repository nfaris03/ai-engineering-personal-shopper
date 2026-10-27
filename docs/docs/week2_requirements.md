# Topic 2 — Project Framing and Requirements

## 0. Project Framing and Application Scope

### 0.1 Project Name

AI-Powered Personal Shopper for Online Shopping Platforms

### 0.2 Problem Statement

Online shoppers often need to compare product prices, specifications, and customer reviews across different e-commerce platforms such as Shopee and Lazada. This process can be time-consuming and makes it difficult to identify products that provide good value and match individual preferences.

This project proposes an AI-powered personal shopper that compares available product information, analyses customer reviews using Natural Language Processing (NLP), and ranks products according to user preferences.

### 0.3 Problem Evidence

- **Amazon Product Reviews and Metadata Dataset:** Provides product information and customer reviews that can support product comparison and sentiment analysis experiments.
- **Lazada Open Platform:** Provides developer resources for accessing product information through permitted APIs, subject to platform access and permissions.

These sources can support initial development and testing. Cross-platform data availability and access must be verified before implementation.

### 0.4 Existing Approaches

**E-commerce recommendation systems**
- Recommend products based on product features and user behaviour.
- Limitation: Recommendations on individual platforms may not support direct comparison across different platforms.

**NLP-based sentiment analysis**
- Estimates positive, negative, or neutral sentiment in customer reviews.
- Limitation: Sentiment alone may not represent product quality or suitability for every user.

**E-commerce platform APIs**
- Provide structured product information where access is permitted.
- Limitation: Data fields, rate limits, and access permissions vary by platform.

### 0.5 Engineering Gap

The main challenge is combining available product information, review sentiment, and user preferences into one comparison workflow. Product matching, inconsistent specifications, data availability, and sentiment reliability must be considered.

The project focuses on developing a practical prototype rather than assuming unrestricted access to every e-commerce platform.

### 0.6 Project Objectives

- **O1:** Develop a web application that compares selected products from supported data sources.
- **O2:** Implement NLP-based customer review sentiment analysis and preference-based product ranking.
- **O3:** Evaluate sentiment performance, recommendation relevance, and system response time.

### 0.7 Intended Users

Online shoppers who want to compare products, understand customer feedback, and identify suitable products based on their preferences and budget.

### 0.8 Application Scope

**Supported tasks**
- Search

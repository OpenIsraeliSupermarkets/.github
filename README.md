
## V0: Current State
### Historical Data:
- Retained in Kaggle, ensuring no data loss.
- Future possibility to load data into an on-demand API.

### On-Demand:
- Basic API to get data like the old interface, which makes the old way of accessing data obsolete.

### Infrastructure: 
Running on small unstable intance.

---
# Project Roadmap


### Next Goal: Public Supermarket Data Website
### Goal:
- GA application to access supermarket data.

### Potential customers:
- Any customer currently accessing the website directly.

### How:
- Running on a stable infrastructure (remote server).
- API accessible to support a few dozen customers.
- Reliable data processing.
- Data served according to each chain’s schema format.
- Only daily data avaliable in the API.
- Understanding minimal hosting requirements.

### Additional Goals:
- Hosting a hackathon to solve DS-related challenges:
  - Transform Kaggle dataset into a hackathon challenge.
  - Organize and run the hackathon.
- Cloud Infrastructure:
  - Create a landing page (AWS required).

---
## V2: Supporting Formatted Interactions
### Goal:
- Serve one schema format across all chains.
- Support search pipeline from natural language queries.

### Customers:
- GenAI applications.

---

## V3: Supporting Product Comparison
### Goal:
- Enable price comparison across supermarket chains.

### Customers:
- Comparison applications.
- Price comparison platforms.

### How:
- Minimal data retention for in-day changes.
- Expose an **Alternatives API** that:
  - Finds equivalent products across different chains.

---
## V4: Supporting Time-Series Analysis
### Goal:
- Provide price predictions and trend detection.

### Customers:
- Price prediction models.
- Trend detection applications.

### How:
- Load historical data from Kaggle.

---

## V4: Exposing Web Page and User Access
### Goal:
- Provide monitoring and visibility for data pipeline status and quality.

### Customers:
- Internal stakeholders and users.

### How:
- **Monitoring Page:**
  - Based on MongoDB collection, create a page to track data pipeline status.
- **Data Quality Metrics Page:**
  - Based on MongoDB collection, publish metrics about data quality.

---





# Work Breakdown & Definition of Done (DoD)

### V1: Reducing Latency
- **Scrapers:**
  - Support writing XML to a stream (no IO to hard drive).
  - Use queues to populate scrapers with data nodes (one queue per chain).
- **Scrapers:**
  - Write execution status into MongoDB instead of JSON files.
  - Create a new collection for all scraper execution statuses.
- **Parsers:**
  - Pull data from the queue instead of reading from the hard drive.
  - Write parsed results to MongoDB (one collection per file type and chain, keeping all versions).
  - Investigate latency reduction strategies.
- **Stability Improvements:**
  - Perform scraper stress tests (analyze impact of high CPU allocation on timeouts).
  - Error analysis to ensure correct data publication to Kaggle.
- **Kaggle Dump:**
  - Develop a process to transform MongoDB data into a Kaggle dataset and publish it.

### V2: Data Analysis
- **Schema Linking:**
  - Solve schema linking between supermarket chains.
  - Compute product prices across chains.
- **Promotions:**
  - Implement a method to apply promotions to product prices.
- **Schema Transformation:**
  - Given a CSV, execute schema transformations.
  - Evaluate transformations on random Kaggle data versions.
  - Plan for processing all Kaggle data into MongoDB.

### V2: Search
- **Schema Engine:**
  - Implement a search engine that allows text searches across any textual column.
  - Merge and pre-filter lists based on search queries.

### V3: Time-Series Data
- **Kaggle Load:**
  - Load Kaggle datasets into MongoDB.

---

## Additional Action Item
- **Create README:**
  - Document project state and roadmap clearly for contributors.


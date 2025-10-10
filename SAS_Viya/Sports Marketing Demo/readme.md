# Sports Marketing Demo
The demo highlights the challenges faced by a sports organization in leveraging customer data for effective marketing. Issues such as duplicate records, inconsistent data from various sources, and the inability to unify this data hinder the organization’s ability to identify and target meaningful customer segments. Additionally, the organization is not utilizing unstructured data like fan feedback, which holds valuable insights. The proposed solution involves implementing a comprehensive data quality and analytics framework powered by SAS Viya to address these issues. This framework will unify structured and unstructured data, address non-standardized and dirty data, to build a golden record for individual customers and households.

 

**Demo Outline:**

- SAS Information Governance
  - Identify data quality issues across datasets leveraging **data profiling** (pattern analysis/frequency distribution)
- SAS Visual Analytics – Despair of Disparate Data
  - Visualize the same person/household across different domains (merchandise, tickets, fan surveys) with inconsistent/non-standardized Contact Information columns (Name, Address, Phone Number, etc.)
  - Demonstrate need for **golden record/master data** for individual and household to aggregate activity across domains
- SAS Studio Flows – Data Quality and Data Integration
  - Data quality workflows that standardize, cluster, matching, and de-duplicate (entity resolution) to create a master dataset for a specific domain
    - Include address Verification/email Verification with Loqate
  - Demonstrate creating a golden record between all domains
    - For each domain, a master dataset is created that standardizes and matches individuals
    - Subsequently, those domains are joined together to create a **master golden record** along with accompanying contact information (ID per domain, most recent address, non-missing phone number/email)
- SAS Visual Analytics – Cleaned Golden Records with Summation Totals
  - After creating a golden record/master data, aggregated report page with master data visualizing a 360 Fan/Household Profile to show activity different domains (primary/secondary ticket sales, merchandise, surveys)

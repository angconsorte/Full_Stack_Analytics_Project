# Full Stack Analytics Project
An end-to-end data analytics pipeline integrating NYC health inspection data with user ratings to uncover correlations between restaurant price, cuisine, and safety compliance.

**Built with:** Jupyter Notebook · Python · SQL (SQLite) · pandas · REST API · Matplotlib · Seaborn

**Note:** This was a guided capstone project completed as part of the DeepLearning.AI data analytics curriculum.

### Situation (The Challenge)
As a data analyst at a consulting firm, the challenge was to support restaurant owners in optimizing their business performance. The primary pain point for clients is maintaining high health standards while managing operational characteristics. The firm needed a data-driven approach to understand if specific restaurant characteristics (such as price level or cuisine category) systematically correlate with better or worse health inspection performance.

### Task (The Objective)
The objective was to build a data pipeline to acquire, clean, and analyze disparate datasets to answer key business questions:
* How do health inspection scores vary across different cuisine types?
* Is there a relationship between a restaurant's price level and its inspection grade?
* Can we aggregate data from web sources and APIs into a unified database for analysis?

### Action (The Solution)
I implemented a data processing workflow using Python:

1.  **Data Extraction**:
    * Web-scraped DOHMH New York City Restaurant Inspection Results using `pandas` to parse HTML tables.
    * Developed a script to consume a restaurant information API, handling pagination to retrieve thousands of records regarding ratings and price levels.
2.  **Data Cleaning & Transformation**:
    * Standardized inconsistent text data (e.g., street abbreviations like "AVE" vs. "AVENUE", removing special characters from restaurant names).
    * Converted temporal data to proper datetime objects for time-series validity.
    * Mapped qualitative price levels (e.g., "$$$") to numeric values for quantitative analysis.
3.  **Data Storage**:
    * Architected a local SQLite database (`restaurant_data.db`) to store the cleaned datasets (`inspections` and `ratings` tables), enabling efficient SQL querying.
4.  **Analysis & Visualization**:
    * Executed SQL queries to aggregate inspection scores by cuisine and location.
    * Created visualization functions using `Seaborn` and `Matplotlib` to display average health scores by cuisine type and price point.

### Result (The Impact)
The analysis integrated thousands of inspection records with business metadata, revealing four critical insights for client strategy:

* **High Price ≠ Clean Kitchen**: Analysis revealed that luxury pricing has zero correlation with better health scores; safety cannot be "bought."
* **Reviews Mask Risk**: Data showed that high customer ratings often hide failing health inspections, proving that platforms like Yelp are poor metrics for safety.
* **Geography Drives Failure**: Identified specific neighborhoods that cluster poor scores due to infrastructure issues, highlighting the need to screen new locations for structural risks (e.g., pests).
* **Safety is a Differentiator**: Since customers cannot "taste" cleanliness, the data suggests that aggressively marketing an "A" grade is a major competitive advantage.

### Tech Stack
* **Language**: Python
* **Notebook**: Jupyter Notebook (Google Colab)
* **Data Manipulation**: pandas (cleaning, HTML scraping, `read_sql` / `to_sql`)
* **Database**: SQLite, queried with SQL (`JOIN`, `GROUP BY` aggregations)
* **Data Extraction**: Requests (API), Pandas (HTML Scraping)
* **Visualization**: Matplotlib, Seaborn
* **Environment Management**: `dotenv`, `os`

---
This project was developed using an AI-assisted workflow to optimize library dependencies and prompt engineering.

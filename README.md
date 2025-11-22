End-to-End Stadium Supply Chain Optimization Engine
Project Overview
This project implements a full-stack Data Science and Operations Research pipeline designed to optimize inventory logistics for major sporting venues.

By moving beyond static averages, this system establishes a Digital Twin simulation of the stadium economy. It integrates real-world variables—including weather patterns, betting market odds, and historical attendance—to simulate individual transaction-level data. This synthetic data trains a Machine Learning model to forecast demand, the results of which feed into a Linear Programming solver to prescribe optimal inventory orders under strict storage and budget constraints.

Technical Architecture & Skills
This project demonstrates the complete lifecycle of an advanced analytics product:

Data Engineering (ETL Pipeline) Objective: Construct a normalized relational database to serve as the single source of truth. Implementation: Built a Python ETL pipeline extracting NFL schedule data via API and scraping historical attendance figures using BeautifulSoup. Data is transformed and loaded into a local SQLite database with enforced schema integrity (Primary/Foreign Keys).

Stochastic Simulation (Data Generation) Objective: Overcome data scarcity by generating a robust training dataset. Implementation: Engineered a Chaos Simulator to generate 1,000,000+ synthetic sales transactions. The simulation utilizes conditional probability distributions to model complex crowd behaviors, such as reduced consumption during blowout games or increased demand during high-scoring matchups.

Machine Learning (Demand Forecasting) Objective: Predict aggregate game-day demand based on external factors. Implementation: Trained a Random Forest Regressor to predict sales volume based on features including Temperature, Vegas Odds (Spread/Total), and Attendance. Result: Achieved a 1.24% Mean Absolute Percentage Error (MAPE) on the holdout test set. Key Insight: Feature importance analysis revealed that betting market odds (specifically the Over/Under) were a significant predictor of per-capita sales volume, validating the hypothesis that game excitement correlates with consumption.

Operations Research (Optimization) Objective: Prescribe specific inventory order quantities to maximize profit. Implementation: Formulated and solved a Linear Programming (LP) problem using the PuLP library. The model solves the News Vendor Problem by optimizing decision variables (Beer, Hot Dogs, Soda) against constraints including storage capacity, spoilage costs, and minimum service levels.

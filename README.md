# plsql-window-functions-afanyu-emmanuel

1. Business Context
Real is a US-based real estate brokerage (onereal.com
) that helps clients buy, sell, rent, and finance properties. The company supports both buyers and sellers and also assists clients in obtaining mortgages. With over 2,500 agents and hundreds of monthly clients, Real handles a very large amount of data from agents, clients, properties, and transactions.

  Data Challenge
  Managing and analyzing this data is difficult. The brokerage needs to track top-performing agents, top property types, and locations, while also monitoring income, growth, and client activity. Without proper analytics, it is hard for managers to make data-driven decisions.
  
  Expected Outcome
  The analysis will reveal:
  
  Top-selling agents by region and month
  
  Top-selling properties, categories, and locations
  
  Monthly revenue trends and growth patterns
  
  Client segmentation by spending
  
  Seasonal or time-based insights on property sales and mortgages

2. Success Criteria

  To solve this, I applied five window functions:
  
  Top 5 agents per month and region → RANK()
  
  Running monthly income totals → SUM() OVER()
  
  Month-over-month income growth → LAG()
  
  Client quartiles by spending → NTILE(4)
  
  3-month moving average of transactions → AVG() OVER()

3. Database Schema

  I design four related tables:
  
  Agents – stores real estate agents
  
  agent_id (PK), name, region
  
  Clients – stores buyers, sellers, and renters
  
  client_id (PK), name, type, region
  
  Properties – stores property details
  
  property_id (PK), title, category, location
  
  Transactions – records all deals
  
  transaction_id (PK), client_id (FK), property_id (FK), agent_id (FK), sale_date, amount

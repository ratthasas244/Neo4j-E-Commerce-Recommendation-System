Here is the comprehensive README.md in English, professionally formatted for your resume or GitHub, without emojis, and based on the technical details from your report.

Markdown

# E-Commerce Product Recommendation System (Neo4j Graph Database)

This project was developed as part of the CP242 Database Systems course at Srinakharinwirot University. It demonstrates the application of Graph Databases in solving complex data relationship challenges within e-commerce platforms, specifically focusing on personalized recommendation engines.

## 1. Executive Summary
The system leverages the power of Neo4j, a NoSQL Graph Database, to analyze relationships between users, products, and shops. Unlike traditional Relational Databases (RDBMS) that require heavy JOIN operations, this system utilizes high-performance graph traversals to provide real-time product recommendations based on individual user behavior.

## 2. Key Features
* **Personalized Recommendation Engine:**
    * **Category-Based:** Analyzes user purchase history to suggest products from the user's most frequently bought categories.
    * **Shop-Based:** Recommends new arrivals or popular items from shops the user has previously interacted with (Brand Loyalty).
* **Weighted Relationship Logic:** Implements a `count` property on the `BOUGHT` relationship to quantify user interest levels, allowing the system to rank recommendations by relevance.
* **Role-Based Access Control (RBAC):** Features a secure authentication system that distinguishes between regular Users and Administrators, restricting sensitive CRUD operations to authorized personnel.
* **Full CRUD Operations:** Comprehensive management of Nodes (Account, Product, Shop) and Relationships (Bought, From) using Cypher Query Language (CQL).

## 3. Data Modeling (Graph Structure)

### Nodes
* **Account:** Stores user credentials and permissions (username, email, password, role).
* **Product:** Contains item details (productName, productPrice, category, productTags).
* **Shop:** Stores vendor information (shopName, shopAddress, shopPhone).

### Relationships (Edges)
* **BOUGHT:** Connects an `Account` to a `Product` (includes a `count` property for frequency tracking).
* **FROM:** Connects a `Product` to its originating `Shop`.



## 4. Tech Stack
* **Database:** Neo4j (Graph Database)
* **Backend:** Node.js & Express.js
* **Database Driver:** neo4j-driver for seamless Node.js integration.
* **Infrastructure:** Docker Desktop for containerized database management.
* **API Testing:** Postman for endpoint validation and integration testing.

## 5. Technical Implementation (Cypher Query)

Example query for recommending products from categories the user is interested in, excluding items already purchased:

```cypher
MATCH (u:Account {username: "target_user"})-[:BOUGHT]->(p:Product)
WITH u, p.category AS preferred_category, count(*) AS weight
MATCH (rec:Product {category: preferred_category})
WHERE NOT (u)-[:BOUGHT]->(rec)
RETURN rec.productName, rec.productPrice, weight
ORDER BY weight DESC
LIMIT 10
6. Installation and Setup
Deploy Neo4j via Docker:

Bash

docker run \
    --name neo4j-ecommerce \
    -p 7474:7474 -p 7687:7687 \
    -d \
    --env NEO4J_AUTH=neo4j/your_password \
    neo4j:latest
Backend Setup:

Bash

npm install
npm start
7. Key Learnings
Designing Graph-first schemas focused on data interconnectedness rather than static tables.

Proficiency in Cypher Query Language (CQL) for complex data analytics.

Implementing Full-stack integration between a NoSQL Graph Database and a Node.js REST API.

Utilizing Docker for consistent development and deployment environments.

Developers: Team "SELECT * FROM Heart"

Jirat Ukongka (66102010233)

Yanapat Pankasane (66102010236)

Rattasart Chantra (66102010244)

Advisor: Asst. Prof. Dr. Waraporn Viyanant Institution: Srinakharinwirot University

Neo4j Product Recommendation System








A web-based product recommendation system built with Neo4j (Graph Database), Node.js, and Docker.
This project demonstrates how graph-based data modeling can efficiently power personalized recommendations in e-commerce applications.

👥 Project Information

Project Title: Neo4j Product Recommendation System
Course: Database Systems (CP242)
University: Srinakharinwirot University
Group: SELECT * FROM ใจเธอ (B01)

Team Members

Jiratt U Kongkha — 66102010233

Yanapat Pankasem — 66102010236

Ratthasas Chantra — 66102010244

✨ Features

Graph-based data modeling using Neo4j

User–Product–Shop relationship tracking

Purchase-based recommendation logic

Full CRUD operations with Cypher

Dockerized database setup

REST API with Express.js

🧠 System Overview

Entities are represented as nodes and interactions as relationships:

Account → User

Product → Item for sale

Shop → Product owner

Relationships:

(:Account)-[:BOUGHT {count}]->(:Product) — tracks purchase frequency

(:Product)-[:FROM]->(:Shop)

Recommendations are generated based on:

Same product category

Same shop

Highest purchase count

🛠 Tech Stack

Neo4j — Graph Database

Node.js, Express.js — Backend

Docker / Docker Compose — Containerization

Postman — API Testing

🚀 Getting Started
Prerequisites

Docker Desktop

Node.js

1. Clone the Repository
git clone https://github.com/your-username/neo4j-recommendation-system.git
cd neo4j-recommendation-system

2. Start Neo4j with Docker
docker-compose up -d


Neo4j Browser:
👉 http://localhost:7474/browser

3. Install Dependencies
npm install

4. Run the Server
nodemon server.js


API will be available at:
👉 http://localhost:3000

🔗 API Endpoints (CRUD)
Create Node

POST /nodes

{
  "label": "Person",
  "properties": { "id": "u1", "name": "Alice", "age": 25 }
}

Read Nodes

GET /nodes/:label

Update Node

PUT /nodes/:label/:id

{
  "properties": { "age": 26 }
}

Delete Node

DELETE /nodes/:label/:id

🗂 Data Model
Node Types

Account

{ "id": "", "username": "", "email": "", "role": "", "password": "" }


Product

{ "id": "", "productName": "", "productCategory": "", "productPrice": "", "shopId": "" }


Shop

{ "id": "", "shopName": "", "shopAddress": "", "shopPhone": "" }

📈 Recommendation Logic

When a user purchases a product, a BOUGHT relationship is created or updated.

The system analyzes:

Most purchased categories

Most purchased shops

Products with the highest interaction count are recommended.

🐳 Neo4j Cypher Shell (Docker)
docker exec -it neo4j-container cypher-shell -u neo4j -p Neo4j12345*


Exit:

:quit

📁 Project Structure
.
├── docker-compose.yml
├── server.js
├── package.json
├── neo4j_database/
├── models/
├── controllers/
└── views/

📄 License

This project is for educational purposes only.
You are free to modify and extend it.

📚 References

Neo4j Documentation: https://neo4j.com/docs/

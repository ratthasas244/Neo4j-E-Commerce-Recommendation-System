# Neo4j NoSQL Graph Database - Recommendation System

A product recommendation system built using Neo4j NoSQL Graph Database to provide personalized suggestions based on individual user behavior and interests.

## Project Overview
This project was developed as part of the CP242 Database Systems course at Srinakharinwirot University, Semester 2, Academic Year 2024. The system tracks user interactions, such as purchase frequency per category and shop, to analyze preferences and recommend products effectively.

### Objectives
1. To develop a web-based recommendation system that adapts to the specific behaviors and interests of each user.
2. To study and implement a Graph Database (Neo4j) for managing complex data relationships.

## Tech Stack
* Database: Neo4j (NoSQL Graph Database)
* Runtime: Node.js
* Backend Framework: Express.js
* Containerization: Docker Desktop
* API Testing: Postman

## Data Model
The system utilizes Nodes and Relationships (Edges) to represent data connections:

### Nodes
* Account: User information including ID, Username, Email, Role, and Password.
* Product: Product details including Name, Price, Category, and Description.
* Shop: Store information including Name, Address, and Phone Number.

### Relationships
* Account -[:BOUGHT]-> Product: Includes a "Count" property to track purchase frequency.
* Product -[:FROM]-> Shop: Links each product to its respective store.



## Installation and Setup

### 1. Database Configuration (Docker)
Create a docker-compose.yml file in the root directory:

```yaml
services:
  neo4j:
    image: neo4j:latest
    container_name: neo4j-container
    environment:
      - NEO4J_AUTH=neo4j/Neo4j12345*
    ports:
      - "7474:7474"
      - "7687:7687"
    volumes:
      - ./neo4j_database/neo4j_data:/data
    restart: always

เข้าใจแล้วครับ ผมนำเนื้อหาทุกส่วนที่คุณระบุ ตั้งแต่ Recommendation Logic, Project Conclusion ไปจนถึง Acknowledgments และ References มารวมกันให้อยู่ภายในโครงสร้าง Markdown ที่สมบูรณ์แบบเดียว เพื่อให้คุณก๊อปปี้ไปวางในไฟล์ README.md ได้ทันทีครับ

Markdown

# Neo4j NoSQL Graph Database - Recommendation System

A product recommendation system built using Neo4j NoSQL Graph Database to provide personalized suggestions based on individual user behavior and interests.

## Project Overview
This project was developed as part of the CP242 Database Systems course at Srinakharinwirot University, Semester 2, Academic Year 2024. The system tracks user interactions, such as purchase frequency per category and shop, to analyze preferences and recommend products effectively.

### Objectives
1. To develop a web-based recommendation system that adapts to the specific behaviors and interests of each user.
2. To study and implement a Graph Database (Neo4j) for managing complex data relationships.

## Tech Stack
* Database: Neo4j (NoSQL Graph Database)
* Runtime: Node.js
* Backend Framework: Express.js
* Containerization: Docker Desktop
* API Testing: Postman

## Data Model
The system utilizes Nodes and Relationships (Edges) to represent data connections:

### Nodes
* Account: User information including ID, Username, Email, Role, and Password.
* Product: Product details including Name, Price, Category, and Description.
* Shop: Store information including Name, Address, and Phone Number.

### Relationships
* Account -[:BOUGHT]-> Product: Includes a "Count" property to track purchase frequency.
* Product -[:FROM]-> Shop: Links each product to its respective store.



## Installation and Setup

### 1. Database Configuration (Docker)
Create a docker-compose.yml file in the root directory:

```yaml
services:
  neo4j:
    image: neo4j:latest
    container_name: neo4j-container
    environment:
      - NEO4J_AUTH=neo4j/Neo4j12345*
    ports:
      - "7474:7474"
      - "7687:7687"
    volumes:
      - ./neo4j_database/neo4j_data:/data
    restart: always
Run the command:

Bash

docker-compose up -d
2. Backend Setup
Bash

npm init
npm install express neo4j-driver nodemon body-parser
nodemon server.js
Recommendation Logic
The system generates recommendations based on the highest "Count" value within the "BOUGHT" relationship in two ways:

Category-based: Suggests products within the same category as previously purchased items.

Shop-based: Suggests products from shops the user has frequently interacted with.

Project Conclusion
The project successfully implemented a personalized product recommendation system using Neo4j NoSQL Graph Database. The use of Nodes and Edges provided excellent efficiency and flexibility in managing and retrieving complex relational data for the website. Despite various challenges during development, this project serves as a valuable resource for further study and extension of graph database applications in commercial systems.

Project Team (Group B01)
Jirath Ukongka (66102010233)

Yanapat Pankasame (66102010236)

Rattasart Jantra (66102010244)

Acknowledgments
Instructor: Assistant Professor Dr. Waraporn Viyanont

Course: CP242 Database Systems, Srinakharinwirot University

References
[k]code. (2022). Neo4j Docker quick start.

Neo4jOfficial. (2025). Neo4j Documentation.

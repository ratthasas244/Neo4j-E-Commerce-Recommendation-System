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

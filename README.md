# Neo4j NoSQL Graph Database - Recommendation System

[cite_start]A product recommendation system built using Neo4j NoSQL Graph Database to provide personalized suggestions based on individual user behavior and interests[cite: 5].

## Project Overview
[cite_start]This project was developed as part of the CP242 Database Systems course at Srinakharinwirot University, Semester 2, Academic Year 2024[cite: 3]. [cite_start]The system tracks user interactions, such as purchase frequency per category and shop, to analyze preferences and recommend products effectively[cite: 55, 57].

### Objectives
1. [cite_start]To develop a web-based recommendation system that adapts to the specific behaviors and interests of each user[cite: 5].
2. [cite_start]To study and implement a Graph Database (Neo4j) for managing complex data relationships[cite: 5].

## Tech Stack
* [cite_start]Database: Neo4j (NoSQL Graph Database) [cite: 5]
* [cite_start]Runtime: Node.js [cite: 18]
* [cite_start]Backend Framework: Express.js [cite: 27]
* [cite_start]Containerization: Docker Desktop [cite: 19]
* [cite_start]API Testing: Postman [cite: 33]

## Data Model
[cite_start]The system utilizes Nodes and Relationships (Edges) to represent data connections[cite: 5]:

### Nodes
* [cite_start]Account: User information including ID, Username, Email, Role, and Password[cite: 55].
* [cite_start]Product: Product details including Name, Price, Category, Description, and Image URL[cite: 55, 56].
* [cite_start]Shop: Store information including Name, Address, and Phone Number[cite: 56].

### Relationships
* [cite_start]Account -[:BOUGHT]-> Product: Includes a "Count" property to track purchase frequency[cite: 56].
* [cite_start]Product -[:FROM]-> Shop: Links each product to its respective store[cite: 56].

## Installation and Setup

### 1. Database Configuration (Docker)
[cite_start]Create a `docker-compose.yml` file in the root directory with the following configuration[cite: 19]:

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

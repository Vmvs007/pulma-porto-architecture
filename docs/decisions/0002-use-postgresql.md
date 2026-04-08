# 0002 - Use PostgreSQL

## Status
Accepted

## Context
The system requires a relational database to support transactional business operations and structured data.

The main needs include:
- reliable persistence
- transactional consistency
- support for relationships between entities
- good querying capabilities
- maturity and stability in production environments

The team evaluated the need for a document database, but the current domain appears highly structured and relational in nature.

## Options Considered
- PostgreSQL
- MySQL
- MongoDB

## Decision
We will use PostgreSQL as the primary database for the system.

PostgreSQL was chosen because it provides strong relational capabilities, ACID transactions, mature tooling, good performance, and flexibility for future growth.

It is well suited for business systems that require data integrity and clear relational modelling.

## Consequences
### Positive
- Strong support for relational data modelling
- Reliable transactional behaviour
- Mature and widely adopted technology
- Good support for indexing, constraints, and advanced queries
- Works well with most backend frameworks and ORMs

### Negative
- Less natural for highly dynamic or schema-flexible data than a document database
- Requires careful schema design and migration management

### Neutral
- If future needs emerge for specific read models, analytics, or unstructured data, additional storage technologies may be evaluated separately
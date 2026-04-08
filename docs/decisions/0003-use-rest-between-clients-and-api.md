# 0003 - Use REST Between Clients and API

## Status
Accepted

## Context
The system needs a communication style between frontend clients and the backend application.

The main goals are:
- simplicity
- broad compatibility
- ease of implementation
- clear request/response interactions
- support for web and possibly mobile clients

Alternative communication styles such as GraphQL and gRPC were considered, but they introduce additional complexity or are less aligned with the current needs of the project.

At this stage, the system does not require highly optimized binary protocols or complex client-driven query flexibility.

## Options Considered
- REST
- GraphQL
- gRPC

## Decision
We will use REST as the communication style between clients and the backend API.

The API will expose resource-oriented HTTP endpoints using standard methods such as:
- GET
- POST
- PUT
- PATCH
- DELETE

Responses will use JSON.

REST was chosen because it is easy to understand, well supported by tools, and appropriate for the current scale and complexity of the system.

## Consequences
### Positive
- Simple and familiar model for most developers
- Excellent tooling and ecosystem support
- Easy integration with web frontends, mobile apps, and external systems
- Good fit for CRUD-oriented and business-oriented APIs

### Negative
- Can lead to over-fetching or under-fetching in some scenarios
- More rigid than GraphQL for complex client-driven data needs
- Does not provide the performance characteristics of gRPC for high-throughput internal communication

### Neutral
- REST is the chosen default for client-to-server communication
- Other integration styles may still be considered later for internal or specialized use cases
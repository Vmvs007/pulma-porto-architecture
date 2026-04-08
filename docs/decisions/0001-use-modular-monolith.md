# 0001 - Use Modular Monolith

## Status
Accepted

## Context
The system is being developed by a small team and the business domain is still evolving.

At this stage, the project needs:
- fast delivery
- low operational complexity
- clear internal structure
- room for future evolution

A distributed architecture such as microservices was considered, but it would introduce additional complexity in deployment, observability, inter-service communication, fault handling, and data consistency.

The team wants a solution that is simple to develop and operate, while still encouraging good separation of concerns.

## Options Considered
- Traditional monolith
- Modular monolith
- Microservices

## Decision
We will implement the system as a modular monolith.

The application will be deployed as a single unit, but internally it will be organized into modules aligned with business capabilities.

Each module should encapsulate its own responsibilities, rules, and data access boundaries as much as possible.

Examples of modules may include:
- Orders
- Customers
- Products
- Notifications
- Identity and Access

## Consequences
### Positive
- Simpler deployment and operations
- Lower infrastructure and DevOps overhead
- Easier local development and debugging
- Better maintainability than a traditional unstructured monolith
- Clearer path to future extraction of modules if needed

### Negative
- Requires discipline to preserve module boundaries
- Independent scaling of modules is not possible
- There is a risk of internal coupling if the architecture is not enforced

### Neutral
- This decision can be revisited in the future if business scale, team size, or operational needs justify a more distributed approach
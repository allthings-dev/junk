# junk
Junk

## Project Workflow

```mermaid
flowchart TD
    A[Start] --> B{Is it working?}
    B -->|Yes| C[Great!]
    B -->|No| D[Debug]
    D --> E[Fix issue]
    E --> B
    C --> F[Deploy]
    F --> G[End]
```

## Sequence Diagram Example

```mermaid
sequenceDiagram
    participant User
    participant App
    participant Database
    
    User->>App: Request data
    App->>Database: Query
    Database-->>App: Return results
    App-->>User: Display data
```

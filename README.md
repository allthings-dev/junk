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


## Gantt Chart - Project timelines

```mermaid
gantt
    title Web App Development Timeline
    dateFormat  YYYY-MM-DD
    section Planning
    Requirements    :done, req, 2024-01-01, 2024-01-15
    Design         :done, des, 2024-01-10, 2024-01-25
    section Development
    Frontend       :active, front, 2024-01-20, 2024-02-20
    Backend        :back, after front, 30d
    Database       :db, 2024-01-25, 2024-02-10
    section Testing
    Unit Tests     :test1, after back, 10d
    Integration    :test2, after test1, 5d
    section Deployment
    Production     :prod, after test2, 3d
```

## Class Diagram - Object-oriented design

```mermaid
classDiagram
    class User {
        -string email
        -string password
        -string name
        +login()
        +logout()
        +updateProfile()
    }
    
    class Order {
        -int id
        -Date createdAt
        -float total
        +calculateTotal()
        +addItem()
        +removeItem()
    }
    
    class Product {
        -int id
        -string name
        -float price
        -int stock
        +updateStock()
        +getPrice()
    }
    
    User ||--o Order : places
    Order ||--o Product : contains
```


## State Diagrams - System states and transitions

```mermaid
stateDiagram-v2
    [*] --> Idle
    Idle --> Loading : start_request
    Loading --> Success : request_complete
    Loading --> Error : request_failed
    Success --> Idle : reset
    Error --> Idle : retry
    Error --> Loading : retry_request
    Success --> [*] : cleanup
    Error --> [*] : cleanup
```


## Entity Relationship Diagrams - Database schemas

```mermaid
erDiagram
    CUSTOMER {
        int customer_id PK
        string first_name
        string last_name
        string email
        date created_at
    }
    
    ORDER {
        int order_id PK
        int customer_id FK
        date order_date
        float total_amount
        string status
    }
    
    PRODUCT {
        int product_id PK
        string name
        float price
        int stock_quantity
        string category
    }
    
    ORDER_ITEM {
        int order_id FK
        int product_id FK
        int quantity
        float unit_price
    }
    
    CUSTOMER ||--o{ ORDER : places
    ORDER ||--o{ ORDER_ITEM : contains
    PRODUCT ||--o{ ORDER_ITEM : included_in
```


## User Journey Diagrams - User experience flows

```mermaid
journey
    title User Shopping Experience
    section Discovery
      Visit website     : 5: User
      Browse products   : 3: User
      Search items      : 4: User
    section Purchase
      Add to cart       : 4: User
      Review cart       : 3: User
      Checkout          : 2: User
      Payment           : 1: User
    section Post-Purchase
      Receive confirmation : 5: User
      Track order       : 4: User
      Receive product   : 5: User
      Leave review      : 3: User
```
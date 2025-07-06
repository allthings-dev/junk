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
    participant User1
    participant App1
    participant Database1
    
    User->>App: Request data
    App->Database: Query
    Database-->>App: Return results
    App-->User: Display data
    Note over User1: Client starts process
    User1->>+App1: Request data
    App1-->>-Database1: Query
    Database1-)App1: Return results
    App1--xUser1: Display data
    User1->>User1: Validates data
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
        -List~Order~ orders
        +login()
        +logout()
        +updateProfile()
        +getOrders() List~Order~
    }
    
    class Order {
        -int id
        -Date createdAt
        -float total
        -User user
        -List~Product~ products
        +calculateTotal()
        +addItem(Product)
        +removeItem(Product)
        +getUser() User
    }
    
    class Product {
        -int id
        -string name
        -float price
        -int stock
        +updateStock()
        +getPrice()
    }
    
     User "1" *-- "0..*" Order : contains (composition)
     Order "1" --> "1" Product : references
     note for User "User owns orders completely"
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
    ORDER ||--|| ORDER_ITEM : contains
    PRODUCT ||--o| ORDER_ITEM : included_in
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

```mermaid
pie title My Pie Chart
    "Label 1" : 42.96
    "Label 2" : 50.05
    "Label 3" : 10.01
```

Use HTML/CSS Layout (Recommended)
<div style="display: flex; gap: 20px;">
  <div style="flex: 1;">
    <h3>Q1 Sales</h3>
    
```mermaid
pie title Q1 Revenue
    "Product A" : 45
    "Product B" : 30
    "Product C" : 25
```
  </div>
  <div style="flex: 1;">
    <h3>Q2 Sales</h3>
    
```mermaid
pie title Q2 Revenue
    "Product A" : 40
    "Product B" : 35
    "Product C" : 25
```
  </div>
</div>


Using markdown tables
| Q1 Performance | Q2 Performance |
|----------------|----------------|
| ```mermaid<br>pie title Q1<br>"Sales" : 60<br>"Marketing" : 40<br>``` | ```mermaid<br>pie title Q2<br>"Sales" : 70<br>"Marketing" : 30<br>``` |


Sequential Charts with Clear Separation
## Side-by-Side Comparison

### Before Implementation
```mermaid
pie title Before - Issue Distribution
    "Bug Reports" : 45
    "Feature Requests" : 30
    "Performance Issues" : 25
```

### After Implementation
```mermaid
pie title After - Issue Distribution
    "Bug Reports" : 25
    "Feature Requests" : 50
    "Performance Issues" : 25
```



4. Use Subgraphs in Flowcharts
```mermaid
flowchart TD
    subgraph "Q1 Results"
        A[Sales: 45%]
        B[Marketing: 30%]
        C[Operations: 25%]
    end
    
    subgraph "Q2 Results"
        D[Sales: 50%]
        E[Marketing: 25%]
        F[Operations: 25%]
    end
```
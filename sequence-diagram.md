```mermaid
sequenceDiagram
    participant User
    participant Frontend
    participant Backend
    participant Database

    User->>Frontend: Enter login credentials
    Frontend->>Backend: Send login request
    Backend->>Database: Query user data
    Database-->>Backend: Return user data
    alt Successful login
        Backend-->>Frontend: Send authentication token
        Frontend-->>User: Display logged-in state
    else Failed login
        Backend-->>Frontend: Send error message
        Frontend-->>User: Display error message
    end
erDiagram
    USERS ||--o{ BOOKINGS : places
    RESOURCES ||--o{ BOOKINGS : "is assigned to"
    RESOURCES ||--o{ MAINTENANCE_LOGS : "has history"
    
    USERS {
        uuid id PK
        string email
        string[] certifications
        int reputation_score
    }
    RESOURCES {
        uuid id PK
        string type "PowerTool | Transport"
        string state "Available | InUse | Repair"
        jsonb metadata
    }
    BOOKINGS {
        uuid id PK
        datetime start_time
        datetime end_time
        string status "Active | Completed | Overdue"
    }
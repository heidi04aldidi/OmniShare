useCaseDiagram
    actor "Community Member" as M
    actor "Volunteer Admin" as A
    actor "Automated System" as S

    package "OmniShare API" {
        usecase "Book Resource" as UC1
        usecase "Verify Safety Badge" as UC2
        usecase "Process Pickup/Return" as UC3
        usecase "Audit Maintenance Logs" as UC4
        usecase "Auto-Flag for Repair" as UC5
    }

    M --> UC1
    M --> UC3
    UC1 ..> UC2 : <<include>>
    
    A --> UC3
    A --> UC4
    
    S --> UC5
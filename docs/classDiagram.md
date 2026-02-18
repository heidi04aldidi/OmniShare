classDiagram
    class Resource {
        <<abstract>>
        +uuid id
        +string name
        +calculateRiskScore()*
    }
    class PowerTool {
        +int voltage
        +calculateRiskScore()
    }
    class Vehicle {
        +int fuelLevel
        +calculateRiskScore()
    }
    Resource <|-- PowerTool : Inheritance
    Resource <|-- Vehicle : Inheritance
    User "1" --o "*" Booking : Composition
    Resource "1" --o "*" Booking : Composition
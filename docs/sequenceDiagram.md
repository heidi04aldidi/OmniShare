sequenceDiagram
    autonumber
    Member->>Controller: POST /bookings (itemId)
    Controller->>AuthService: validateMemberBadge(userId, itemType)
    AuthService-->>Controller: Badge Valid
    Controller->>BookingService: createBooking(itemId)
    BookingService->>DB: Start Transaction (Lock Item)
    DB-->>BookingService: Item Locked & Booking Created
    BookingService-->>Controller: Confirm Success
    Controller-->>Member: 201 Created
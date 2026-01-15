#Step 1 - Establish Design Scope

Question 1: Can customers book hotel rooms through the hotels website only? Or we need to support other options such as phone calls?

Question 2: Do customers pay when they make reservations or when they arrive at hotel?

Question 3: Do we require to support cancellations of reservation by customer?

Question 4: Do we want to support demand-based pricing like weekends, long weekends Pricing etc?

Question 5: What is the initial scale that we are building for? Number of hotels, rooms?

Are there any things we need to consider?

### Functional Requirements


## Data Model
A relational database works well with read-heavy and write less frequency workflow.

### hotels
| Field | Type | Notes |
|-----|-----|------|
| hotel_id | UUID | Primary key |
| name | String | |
| address | String | City / geo |
| created_at | Timestamp | |

### rooms
| Field | Type | Notes |
|-----|-----|------|
| room_id | UUID | PK |
| hotel_id | UUID | FK → Hotel |
| room_type_id | String | Deluxe, Suite |
| name | String | |
| capacity | Int | |

### reservations
| Field | Type | Notes |
|-----|-----|------|
| reservation_id | UUID | PK |
| room_id | UUID | FK → Room |
| user_id | UUID | |
| check_in | Date | |
| check_out | Date | |
| status | String | CONFIRMED / CANCELLED |
| created_at | Timestamp | |

### users
| Field | Type | Notes |
|-----|-----|------|
| user_id | UUID | PK |
| first_name | String |  |
| last_name | String |  |
| email | String |  |
| phone | Int |  |

### room_types
| Field | Type | Notes |
|-----|-----|------|
| room_type_id | UUID | PK |
| hotel_id | UUID | FK → hotel |
| date | Timestamp | |
| total_inventory | Int |  |
| total_reserved | Int |  |

### room_pricing
| Field | Type | Notes |
|-----|-----|------|
| room_type_id | UUID | PK |
| date | Timestamp | |
| price | Decimal |  |
| created_at | Timestamp |  |

### notifications
| Field | Type | Notes |
|-----|-----|------|
| notification_id | UUID | PK |
| user_id | UUID | FK → users|
| reservation_id | UUID | FK → reservation |
| is_read | boolean |  |
| created_at | Timestamp |  |

### Concurrency issues


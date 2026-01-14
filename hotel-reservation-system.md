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
| user_id | UUID | PK |

### room_pricing

### Concurrency issues


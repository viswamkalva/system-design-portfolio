## Data Model
A relational database works well with read-heavy and write less frequency workflow.

### Hotel
| Field | Type | Notes |
|-----|-----|------|
| hotel_id | UUID | Primary key |
| name | String | |
| location | String | City / geo |
| rating | Float | |
| created_at | Timestamp | |

### Room
| Field | Type | Notes |
|-----|-----|------|
| room_id | UUID | PK |
| hotel_id | UUID | FK → Hotel |
| room_type | String | Deluxe, Suite |
| price | Decimal | |
| capacity | Int | |

### Reservation
| Field | Type | Notes |
|-----|-----|------|
| reservation_id | UUID | PK |
| room_id | UUID | FK → Room |
| user_id | UUID | |
| check_in | Date | |
| check_out | Date | |
| status | String | CONFIRMED / CANCELLED |
| created_at | Timestamp | |


### Concurrency issues


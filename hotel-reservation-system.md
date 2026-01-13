## Data Model
A relational database works well with read-heavy and write less frequency workflow.

### Hotels
| Field | Type | Notes |
|-----|-----|------|
| hotel_id | UUID | Primary key |
| name | String | |
| address | String | City / geo |
| created_at | Timestamp | |

### Rooms
| Field | Type | Notes |
|-----|-----|------|
| room_id | UUID | PK |
| hotel_id | UUID | FK → Hotel |
| room_type_id | String | Deluxe, Suite |
| name | String | |
| capacity | Int | |

### Reservations
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


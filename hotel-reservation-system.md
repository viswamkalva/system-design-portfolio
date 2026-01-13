### Data Model
A relational database works well with read-heavy and write less frequency workflow.

## Data Model (Schema View)

Hotel(
  hotel_id PK,
  name,
  location,
  rating
)

Room(
  room_id PK,
  hotel_id FK,
  room_type,
  price,
  capacity
)

Reservation(
  reservation_id PK,
  room_id FK,
  user_id,
  check_in,
  check_out,
  status
)


### Concurrency issues


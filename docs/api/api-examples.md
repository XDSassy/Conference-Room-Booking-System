# Conference Room Booking API – Usage Examples

## Authentication
```http
POST /auth/login
Content-Type: application/json

{
  "email": "user@company.com",
  "password": "password123"
}

POST /rooms
Authorization: Bearer <token>
Content-Type: application/json

{
  "id": "room-101",
  "name": "Main Conference Room",
  "capacity": 12,
  "location": "Floor 2"
}

GET /rooms
Authorization: Bearer <token>

GET /availability?roomId=room-101&date=2026-02-01
Authorization: Bearer <token>

POST /bookings
Authorization: Bearer <token>
Content-Type: application/json

{
  "id": "booking-001",
  "roomId": "room-101",
  "startTime": "2026-02-01T10:00:00Z",
  "endTime": "2026-02-01T11:00:00Z",
  "bookedBy": "user@company.com"
}

DELETE /bookings/booking-001
Authorization: Bearer <token>

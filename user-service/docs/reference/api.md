# User Service API

## Endpoints

### `POST /api/v1/users`
Create a new user account.

### `GET /api/v1/users/{id}`
Retrieve user profile and role assignments.

### `PUT /api/v1/users/{id}`
Update user profile fields.

### `DELETE /api/v1/users/{id}`
Soft-delete a user account. Data retained for 90 days.

### `POST /api/v1/users/{id}/roles`
Assign roles to a user.

### `GET /api/v1/users/search`
Search users by email, name, or role. Supports pagination.

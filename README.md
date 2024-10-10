# Go API - Check Account Coin

This is a simple Go API project that checks a user's account balance. It includes:

- Golang Code Structure
- API Authentication
- Middleware
- Package Management

## Features

- A mock database (`mockDB`) for demonstration purposes.
- API endpoint for retrieving user coin balance.
- Simple authentication using tokens.
- JSON response format with status and balance.

## JSON Response Example

```json
{
  "code": "status",
  "coin": "balance"
}
```

## Prerequisites

- Go 1.16 or later installed.
- Familiarity with Go modules.

## Project Structure

```plaintext
/Go-Api
    ├── cmd/api/main.go                        # Entry point of the API
    ├── internal/handlers/api.go               # API route definitions
    ├── internal/middleware/authorization.go   # Authentication middleware
    ├── internal/tools/mockDB.go               # Simulated database for testing
    └── internal/tools/database.go             # Utility functions
```

## API Endpoints

### `GET /account/coin`

Retrieves the coin balance for a user.

#### Request Headers:

- `Authorization: Bearer <token>`

#### Response:

- `200 OK`: Returns user coin balance.
- `401 Unauthorized`: Invalid or missing token.

Example Response:

```json
{
  "code": 200,
  "coin": 1000
}
```

## Authentication

This API uses a simple token-based authentication. The token is passed via the `Authorization` header.

## Middlewares

- **Authentication Middleware**: Ensures valid tokens are provided with API requests.

## How to Run

1. Clone the repository:

   ```bash
   git clone https://github.com/your-repo/Go-Api.git
   ```

2. Navigate into the project directory:

   ```bash
   cd Go-Api
   ```

3. Run the API:
   ```bash
   go run cmd/api/main.go
   ```

## Package Management

This project uses Go Modules for dependency management. All necessary dependencies are listed in the `go.mod` file.

To install dependencies:

```bash
go mod tidy
```

---

## License

This project is licensed under the MIT License.

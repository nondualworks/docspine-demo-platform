# Auth Gateway API

## OAuth2 Endpoints

### `POST /oauth/token`
Exchange authorization code or refresh token for access tokens.

### `GET /oauth/authorize`
Initiate OAuth2 authorization flow.

### `GET /.well-known/jwks.json`
JSON Web Key Set for token verification.

### `POST /oauth/revoke`
Revoke an access or refresh token.

## Token Format

Access tokens are signed JWTs with the following claims:

| Claim | Description |
|-------|-------------|
| `sub` | User ID |
| `scope` | Granted scopes |
| `iss` | Auth gateway issuer URL |
| `exp` | Expiration timestamp |
| `aud` | Target service identifier |

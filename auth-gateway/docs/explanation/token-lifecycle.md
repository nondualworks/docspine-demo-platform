# Token Lifecycle

## Access Tokens

Short-lived JWTs (default: 15 minutes). Verified locally by services using the JWKS endpoint — no call back to the auth gateway needed.

## Refresh Tokens

Long-lived opaque tokens (default: 30 days). Stored encrypted in the auth gateway database. Each refresh produces a new access token AND a new refresh token (rotation).

## Rotation and Revocation

Token rotation prevents replay attacks. When a refresh token is used, the old one is immediately invalidated. If a revoked refresh token is presented, all tokens in the family are revoked (breach detection).

## Session Binding

Refresh tokens are bound to the originating device fingerprint. A token used from a different device triggers re-authentication.

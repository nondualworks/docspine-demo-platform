# Configure SSO

Set up SAML or OIDC single sign-on for enterprise identity providers.

## SAML Configuration

1. Obtain the IdP metadata XML from your identity provider (Okta, Azure AD, etc.)
2. Upload via the admin API:

```bash
curl -X POST /admin/sso/saml \
  -F 'metadata=@idp-metadata.xml' \
  -F 'entity_id=https://auth.example.com'
```

## OIDC Configuration

```yaml
sso:
  oidc:
    issuer: https://login.microsoftonline.com/{tenant}/v2.0
    client_id: ${AZURE_CLIENT_ID}
    client_secret: ${AZURE_CLIENT_SECRET}
    scopes: [openid, profile, email]
```

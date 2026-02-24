# Migrate User Data

Bulk import users from legacy LDAP directories or CSV exports.

## From LDAP

```bash
just user-import --source ldap \
  --ldap-url ldaps://ldap.corp.example.com \
  --base-dn 'ou=people,dc=example,dc=com' \
  --filter '(objectClass=person)' \
  --dry-run
```

Remove `--dry-run` when ready to execute.

## From CSV

Prepare a CSV with columns: `email, first_name, last_name, role`

```bash
just user-import --source csv --file users.csv --dry-run
```

## Post-Migration

After import, users receive a password reset email. Existing SSO users are matched by email and linked automatically.

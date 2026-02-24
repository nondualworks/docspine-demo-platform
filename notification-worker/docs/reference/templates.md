# Notification Templates

## Template Syntax

Templates use Handlebars syntax with variables passed at send time:

```
Hello {{user.first_name}},

Your order {{order_id}} has been confirmed.
```

## Available Templates

| Template | Channels | Variables |
|----------|----------|-----------|
| `order-confirmed` | email, slack | `order_id`, `user` |
| `deploy-complete` | slack, webhook | `service`, `version`, `env` |
| `cve-alert` | email, slack | `cve_id`, `severity`, `service` |
| `password-reset` | email | `user`, `reset_url` |

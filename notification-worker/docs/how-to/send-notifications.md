# Send Notifications

Configure and send notifications through email, Slack, or webhook channels.

## Email

```bash
curl -X POST /api/v1/notifications \
  -d '{
    "channel": "email",
    "to": "user@example.com",
    "template": "order-confirmed",
    "vars": {"order_id": "ord_123"}
  }'
```

## Slack

```bash
curl -X POST /api/v1/notifications \
  -d '{
    "channel": "slack",
    "to": "#checkout-alerts",
    "template": "deploy-complete",
    "vars": {"service": "checkout-api", "version": "1.4.2"}
  }'
```

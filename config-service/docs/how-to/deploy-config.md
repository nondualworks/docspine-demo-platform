# Deploy Config Changes

Roll out configuration changes with zero downtime.

## Gradual Rollout

For risky changes, use percentage-based rollout:

```bash
curl -X PUT /api/v1/config/checkout-api/new_payment_flow \
  -d '{"value": true, "rollout_pct": 10}'
```

Increase the percentage as you gain confidence:

```bash
curl -X PUT /api/v1/config/checkout-api/new_payment_flow \
  -d '{"rollout_pct": 50}'
```

## Instant Rollback

```bash
curl -X PUT /api/v1/config/checkout-api/new_payment_flow \
  -d '{"rollout_pct": 0}'
```

Changes propagate within 5 seconds via server-sent events.

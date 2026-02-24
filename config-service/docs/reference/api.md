# Config Service API

## Endpoints

### `GET /api/v1/config/{service}/{key}`
Retrieve a configuration value with hierarchical resolution.

### `PUT /api/v1/config/{service}/{key}`
Set a configuration value. Triggers change notification to subscribed services.

### `GET /api/v1/flags/{flag_name}`
Evaluate a feature flag for the current context.

### `GET /api/v1/flags`
List all feature flags with their current states and rollout percentages.

## Resolution Order

1. Environment-specific override (`production.checkout-api.timeout`)
2. Service-specific value (`checkout-api.timeout`)
3. Domain default (`checkout.timeout`)
4. Global default (`timeout`)

# Set Up Feature Flags

Create your first feature flag with gradual rollout.

## Step 1: Create the Flag

```bash
curl -X POST /api/v1/flags \
  -d '{
    "name": "dark_mode",
    "description": "Enable dark mode UI",
    "default": false
  }'
```

## Step 2: Enable for Your Team

```bash
curl -X PUT /api/v1/flags/dark_mode/rules \
  -d '{"match": {"team": "platform"}, "value": true}'
```

## Step 3: Gradual Rollout to Everyone

```bash
curl -X PUT /api/v1/flags/dark_mode \
  -d '{"rollout_pct": 25}'
```

## Step 4: Check the Flag in Code

```java
if (configClient.flag("dark_mode").isEnabled()) {
    renderDarkMode();
}
```

## Step 5: Full Release

```bash
curl -X PUT /api/v1/flags/dark_mode \
  -d '{"rollout_pct": 100}'
```

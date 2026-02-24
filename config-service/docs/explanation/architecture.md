# Config Architecture

## Hierarchical Resolution

Configuration values resolve through a 4-level hierarchy:

```
environment override → service value → domain default → global default
```

This allows setting sensible defaults at the global level while permitting per-service and per-environment exceptions.

## Caching Strategy

Services subscribe to config changes via SSE (server-sent events). The local cache is invalidated only when a relevant key changes, not on a polling interval. This gives sub-second propagation with zero unnecessary network calls.

## Audit Trail

Every configuration change is logged with the author, timestamp, previous value, and new value. The audit log is immutable and retained for 2 years for compliance.

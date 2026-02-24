# Base Image Catalog

## Available Base Images

| Image | Tag | OS | Size | Last Scan |
|-------|-----|-----|------|-----------|
| `base/java` | `21-alpine` | Alpine 3.19 | 189MB | 2h ago ✅ |
| `base/java` | `17-alpine` | Alpine 3.18 | 185MB | 2h ago ✅ |
| `base/node` | `20-alpine` | Alpine 3.19 | 124MB | 2h ago ✅ |
| `base/python` | `3.12-slim` | Debian 12 | 156MB | 2h ago ✅ |
| `base/go` | `1.22-alpine` | Alpine 3.19 | 298MB | 2h ago ✅ |

## Usage

```dockerfile
FROM registry.internal.example.com/base/java:21-alpine
COPY target/app.jar /app/app.jar
CMD ["java", "-jar", "/app/app.jar"]
```

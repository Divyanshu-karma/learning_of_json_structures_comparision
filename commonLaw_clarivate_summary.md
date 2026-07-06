# Clarivate Common Law

## Before
```mermaid
flowchart TD
ImageExtraction-->Exception-->pass
```

## After
```mermaid
flowchart TD
ImageExtraction-->logger.warning-->Continue
```

### Major Changes
- Warning logging for image extraction failures

| Before | After |
|---|---|
| Silent image failures | Logged |
| Same fallback | Same fallback |

**Unchanged:** Extraction flow, JSON schema, controller integration.

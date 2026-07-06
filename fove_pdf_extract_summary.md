# Fovea PDF Extractor

## Before
```mermaid
flowchart TD
CLI-->NameError
Domain-->asyncio.run-->RuntimeError
LLM-->SilentFallback
```

## After
```mermaid
flowchart TD
CLI-->orjson.dumps
Domain-->SafeWrapper
LLM-->logger.exception-->Fallback
```

### Major Changes
- CLI serializer fixed
- Event-loop-safe domain enrichment
- Exception logging

| Before | After |
|---|---|
| CLI crash | Valid JSON |
| Async unsafe | Async safe |
| Silent errors | Tracebacks |

**Unchanged:** Extraction logic, JSON schema.

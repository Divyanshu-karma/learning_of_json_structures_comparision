# CompuMark Common Law

## Before
```mermaid
flowchart TD
Cache-->UnlimitedMemory
Vision-->SilentFailure
```

## After
```mermaid
flowchart TD
Cache-->LRUCache
Vision-->LoggedFailure
```

### Major Changes
- LRU image cache
- Exception logging

| Before | After |
|---|---|
| Unlimited cache | LRU |
| Silent failures | Logged |

**Unchanged:** Vision workflow and JSON schema.

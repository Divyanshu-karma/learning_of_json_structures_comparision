# DuckDuckGo Tool

## Before
```mermaid
flowchart LR
Q-->DictCache-->PrivateAPI-->Results
```

## After
```mermaid
flowchart LR
Q-->TTLCache-->PublicAPI-->Results
```

### Major Changes
- TTL bounded cache
- Public `ddgs.text()` API

| Before | After |
|---|---|
| Unlimited cache | TTL + max size |
| Private methods | Public API |

**Unchanged:** Ranking, deduplication, output format.

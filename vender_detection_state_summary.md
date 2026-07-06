# Vendor Detection Controller

## Overview
Main orchestration layer for PDF/DOCX routing and parallel extraction.

## Before
```mermaid
flowchart TD
A[DocumentContext]-->B[Worker Threads]
B-->C[Thread-local Handles]
C-->D[close()]
D-->E[Only caller thread cleaned]
```

## After
```mermaid
flowchart TD
A[DocumentContext]-->B[Worker Threads]
B-->C[Register Handles]
C-->D[Global Registry]
D-->E[close()]
E-->F[All Handles Closed]
```

### Major Changes
- Thread-safe handle registry
- Complete cleanup of worker resources
- Safer import bootstrap

| Before | After |
|---|---|
| Partial cleanup | Full cleanup |
| Leak risk | Controlled |

**Unchanged:** JSON schema, vendor detection, extraction logic.

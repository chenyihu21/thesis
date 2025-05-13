```mermaid
graph LR;
    A[AddrSpace] --> B[va_range];
    A --> C[MemorySet]
    A --> D[PageTable]
    C --> E[MemoryArea]
    E --> F[Backend]
    F --> G[Linear]
    F --> H[Alloc]

```
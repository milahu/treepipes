# treepipes

incremental tree transformers

## status

concept

## example

```
┌──────────┐              ┌──────────┐
│ TSX Text │ ── Parse ──► │ TSX Tree │
└──────────┘              └──────────┘
                               |
                            Compile
                               │
                               ▼
                          ┌──────────┐
                          │ JSX Tree │
                          └──────────┘
                               |
                            Compile
                               │
                               ▼
┌──────────┐              ┌──────────┐
│ JS  Text │ ◄── Print ── │ JS  Tree │
└──────────┘              └──────────┘
```

every arrows is an **incremental** transformer, aka "pipe"

compiler 1 is typescript (tsc)

compiler 2 is a web framework like svelte, solid, qwik ...

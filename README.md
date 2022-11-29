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

## incremental parsing

- http://tree-sitter.github.io/tree-sitter/
- https://lezer.codemirror.net/

## incremental transforming

### term rewriting

- https://en.wikipedia.org/wiki/Rewriting
  - rewriting covers a wide range of methods of replacing subterms of a formula with other terms.
  - https://en.wikipedia.org/wiki/Rewriting#Term_rewriting_systems
- http://rewriting.loria.fr/systems.html
- http://homepages.math.uic.edu/~jan/mcs320/mcs320notes/lec15.html
- https://github.com/kovasb/combinator - Experiments with fast term-rewriting in clojure
- https://github.com/joshrule/term-rewriting-rs - term-rewriting in Rust
- https://github.com/cisco/ChezScheme - fast Scheme interpreter

### incremental computing

https://en.wikipedia.org/wiki/Incremental_computing

https://github.com/janestreet/incremental - A library for incremental computations, in OCaml

https://github.com/adapton/adapton.rust - General-purpose abstractions for incremental computing, in Rust

https://github.com/carlssonia/adaptive - Library for incremental computing, in Haskell

https://doi.org/10.1007/978-3-642-04652-0_1 at https://sci-hub.ru/ - Delta ML - Self-adjusting Computation with Delta ML

https://github.com/MetaBorgCube/IceDust - A language for data modeling and incremental computing of derived values, with Java backend

## incremental printing

TODO

## see also

- https://github.com/milahu/nix-eval-js/blob/main/docs/incremental-computing.md
- https://github.com/milahu/nix-eval-js/blob/main/docs/normal-form.md

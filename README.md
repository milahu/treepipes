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

goal: low latency between input and output

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
- https://github.com/topics/term-rewriting
- https://github.com/noprompt/meander - 800 stars - Clojure
- https://github.com/usethesource/rascal - 300 stars - Java

### incremental computing

- https://en.wikipedia.org/wiki/Incremental_computing
- https://github.com/janestreet/incremental - A library for incremental computations, in OCaml
- https://github.com/adapton/adapton.rust - General-purpose abstractions for incremental computing, in Rust
- https://github.com/carlssonia/adaptive - Library for incremental computing, in Haskell
- https://doi.org/10.1007/978-3-642-04652-0_1 at https://sci-hub.ru/ - Delta ML - Self-adjusting Computation with Delta ML
- https://github.com/MetaBorgCube/IceDust - A language for data modeling and incremental computing of derived values, with Java backend

### differential dataflows

- https://github.com/topics/differential-dataflows
- https://github.com/sixthnormal/clj-3df - 300 stars - Clojure - Clojure(Script) client for Declarative Dataflow
- https://github.com/comnik/declarative-dataflow - 300 stars - Rust - A reactive query engine built on differential dataflow

## incremental printing

TODO

## see also

- https://figwheel.org/docs/reloadable_code.html - live coding system in clojurescript, based on google closure compiler
- https://github.com/vmware/differential-datalog - 1K stars - Java, Rust, Haskell - programming language for incremental computation
  - based on https://github.com/TimelyDataflow/differential-dataflow - 2K stars - Rust - implementation of differential dataflow using timely dataflow on Rust
- https://github.com/milahu/nix-eval-js/blob/main/docs/incremental-computing.md
- https://github.com/milahu/nix-eval-js/blob/main/docs/normal-form.md

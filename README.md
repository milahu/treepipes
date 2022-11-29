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
  - https://github.com/lezer-parser
  - https://github.com/lezer-parser/lr - lezer runtime
  - https://github.com/lezer-parser/generator - lezer parser generator

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
- https://github.com/vmware/differential-datalog - 1K stars - Java, Rust, Haskell - programming language for incremental computation
  - based on https://github.com/TimelyDataflow/differential-dataflow - 2K stars - Rust - implementation of differential dataflow using timely dataflow on Rust

### incremental compilers

- https://www.geeksforgeeks.org/incremental-compiler-in-compiler-design/

#### incremental compiler generators

- https://github.com/nfomon/shok/tree/master/statik - http://statik.rocks/ - https://doi.org/10.1145/2814189.2817278 at https://sci-hub.ru/ - Statik: an incremental compiler generator, Michael Biggs, 2015. Statik allows you to write a compiler as a sequence of "phases" of parsing. Each phase incrementally translates an input list to an output list. For example, your compiler might be constructed as the pipeline: lexer -> parser -> code-generator. The lexer incrementally translates source-code characters to tokens. The parser translates incremental changes to the token list, to an incrementally-updating parse tree. The code-generator responds to the changing parse tree by generating the bytecode for those changes, and emits the bytecode changes incrementally.

### incremental code generators

aka: incremental codegen

- https://github.com/dotnet/roslyn/blob/main/docs/features/incremental-generators.md - C# compiler
- https://andrewlock.net/creating-a-source-generator-part-1-creating-an-incremental-source-generator/

### differential dataflows

focus on GraphQL

- https://github.com/topics/differential-dataflows
- https://github.com/comnik/declarative-dataflow - 300 stars - Rust - A reactive query engine built on differential dataflow
  - https://www.nikolasgoebel.com/2018/09/13/incremental-datalog.html - a method of continuously executing Datalog queries over data streams, by compiling them to differential dataflows
  - https://github.com/sixthnormal/clj-3df - 300 stars - Clojure - Clojure(Script) client for Declarative Dataflow

### reactive programming

- https://en.wikipedia.org/wiki/Reactive_programming
- https://github.com/ReactiveX - a library for composing asynchronous and event-based programs using observable sequences
  - https://github.com/ReactiveX/rxjs - 30K stars - javascript
- https://github.com/sveltejs/svelte - 60K stars - javascript - compiler for reactive user interfaces
- https://github.com/solidjs/solid - 20K stars - javascript - compiler for reactive user interfaces

#### functional reactive programming

- https://en.wikipedia.org/wiki/Functional_reactive_programming
- https://github.com/search?o=desc&q=functional+reactive+programming&s=stars&type=Repositories
- https://github.com/baconjs/bacon.js - 6K stars - javascript
- https://github.com/paldepind/flyd - 2K stars - javascript
- https://github.com/SodiumFRP/sodium-rust - 50 stars - rust - A Functional Reactive Programming (FRP) library for Rust
- https://github.com/staltz/xstream - 2K stars - javascript - functional reactive stream library
- https://github.com/cyclejs/cyclejs - 10K stars - javascript - functional and reactive JavaScript framework
  - based on: [most](https://github.com/cujojs/most), [rxjs](https://github.com/ReactiveX/rxjs), [xstream](https://github.com/staltz/xstream)
  
### program-transformation

- https://github.com/topics/program transformation
- https://github.com/comby-tools/comby - 2K stars - ocaml - A code rewrite tool for structural search and replace that supports ~every language

### source to source compilers

- https://github.com/topics/source-to-source
- https://github.com/topics/transpiler
- https://github.com/topics/refactoring-tools
- https://github.com/onelang/OneLang - 1K stars - javascript - TypeScript, C#, Ruby &rarr; C++, C#, Go, Java, JS, Perl, PHP, Python, Ruby, Swift, TypeScript
  - https://github.com/onelang/OneLang/wiki/OneLang-vs.-Haxe-vs.-Progsbase-comparison
- https://github.com/jarble/transpiler - 400 stars - javascript - A universal translator for programming languages
- https://github.com/usethesource/rascal - 300 stars - java
- https://haxe.org - haxe &rarr; AS2, AS3, C++, C#, Java, JS, Lua, Neko, PHP, Python	
- https://www.progsbase.com/ - java &rarr; Java, C, C++, JavaScript, C#, R, PHP, Python, Visual Basic
- https://github.com/pfusik/cito - cito &rarr; C, C++, C#, Java, JavaScript, Python, Swift, TypeScript, OpenCL C
- https://github.com/oven-sh/bun - 40K stars - Zig - JavaScript runtime, bundler, transpiler, package manager. TS, TSX, JSX, MJS, CJS &rarr; JS
- https://github.com/pseudo-lang/pseudo - 700 stars - python - Pseudo &rarr; JS, Go, C#, Ruby
- https://github.com/jtransc/jtransc - Java, Kotlin, Scala &rarr; X
- https://github.com/akameco/s2s - 300 stars - javascript - based on Babel
- https://github.com/LangTrans/LangTrans - 20 stars - python

### hot module reload

- https://figwheel.org/docs/reloadable_code.html - live coding system in clojurescript, based on google closure compiler
- https://github.com/solidjs/solid-refresh

## incremental printing

TODO

## see also

- https://github.com/milahu/nix-eval-js/blob/main/docs/incremental-computing.md
- https://github.com/milahu/nix-eval-js/blob/main/docs/normal-form.md
- https://github.com/milahu/nix-eval-js/tree/main/docs#lazy-evaluation

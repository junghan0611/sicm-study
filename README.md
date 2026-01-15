# SICM Study - A Journey Toward Understanding

[![한국어](https://img.shields.io/badge/lang-한국어-blue)](README-KO.md)

> "Programming is not just a tool, but a **means of verifying understanding**."
> — Gerald Jay Sussman & Jack Wisdom, SICM Preface

> "Rather than explaining through analogy, we build up mathematical content from the beginning, step by step, to reach our conclusions."
> — Roger Penrose, *The Road to Reality*

This repository is a learning space for the **path to understanding** that leads from *computational thinking* to *classical mechanics*, *differential geometry*, and ultimately to *natural philosophy*.

The name is *sicm-study*, but SICM is just the starting point.
For ultimate goals and philosophical background, see [VISION.md](VISION.md).

## Intellectual Lineage

```
  SICP (1985)                    Foundations of Computational Thinking
  Structure and Interpretation   Scheme language
  of Computer Programs           "Programs = Mathematical Expressions"
       │
       ▼
  SICM (2001)                    Classical Mechanics + Functional Notation
  Structure and Interpretation   scmutils library
  of Classical Mechanics         "Formulas = Code"
       │
       ▼
  FDG (2013)                     Differential Geometry
  Functional Differential        The path to General Relativity
  Geometry
       │
       ▼
  Emmy (2020~)                   Clojure reimplementation
  Computer Algebra System        ClojureScript (runs in browser!)
                                 Clerk notebooks (visualization!)
                                 "Overcoming Scheme's limitations"
```

### Why This Lineage?

The "constructionist learning" that started with Seymour Papert's Logo extends through Gerald Sussman to the core of physics. The idea that *formulas and code are identical* as mathematical tools — this is the foundation of *Universal Science*.

### From Scheme to Clojure

| Feature | scmutils (Scheme) | Emmy (Clojure) |
|---------|-------------------|----------------|
| Runtime | MIT Scheme | JVM, JavaScript |
| Visualization | X Window | Clerk, Browser |
| Ecosystem | Limited | Maven, npm |
| Destructuring | let/ref | `[[_ [r] [rdot φdot]]]` |

## Repository Structure

```
sicm-study/
├── sicp/                # Stage 1: Computational Thinking
│   ├── book/            # sicp.org (complete book, Babel executable)
│   └── info/            # Emacs info version
├── sicm/                # Stage 2: Classical Mechanics
│   ├── book/            # 9 chapters (org-mode)
│   ├── reference/       # Sam Ritchie's Scheme solutions
│   └── my-solutions/    # My solutions
├── fdg/                 # Stage 3: Differential Geometry
│   └── book/            # PDF + Scheme/Clojure code
├── foundations/         # Mathematical Physics Foundations (to be filled)
│   ├── calculus/
│   ├── linear-algebra/
│   ├── differential-geometry/
│   └── variational-principles/
├── tools/
│   ├── emmy/            # Emmy full project (4200+ tests)
│   └── scheme/          # MIT Scheme setup
├── essays/              # Road to Reality (Sam Ritchie essays)
├── README.md            # This file
├── CREDITS.md           # Original author acknowledgments
└── .claude/commands/    # Learning assistant agents
```

## Learning Roadmap

### Phase 0: SICP Foundations (Optional)
- [ ] SICP Chapter 1-2: Procedures, Data Abstraction
- [ ] Scheme/Emacs environment setup
- [ ] Practice running code with Babel

### Phase 1: SICM Preparation
- [ ] Calculus of Variations basics
- [ ] Understanding Lagrangian mechanics concepts
- [ ] Emmy installation and REPL usage

### Phase 2: SICM Core Study
- [ ] Chapter 1: Lagrangian Mechanics
- [ ] Chapter 2: Rigid Bodies
- [ ] Chapter 3: Hamiltonian Mechanics
- [ ] Chapters 4-9: Advanced topics

### Phase 3: Extending to FDG
- [ ] Differential geometry basics
- [ ] Differential Forms
- [ ] FDG book study

## Tools

### Emmy (Recommended)
```clojure
;; Solving Lagrange equations with Emmy
(defn L-central-polar [m U]
  (fn [[_ [r] [rdot φdot]]]
    (- (* 1/2 m (+ (square rdot)
                   (square (* r φdot))))
       (U r))))

(((Lagrange-equations (L-central-polar 'm (literal-function 'U)))
  (up (literal-function 'r) (literal-function 'φ)))
 't)
```

- `tools/emmy/`: Full project included
- `bb repl`: Start REPL
- `bb clerk-watch`: Interactive notebooks

### Scheme (Traditional)
- `sicm/reference/bin/mechanics`: Docker-based scmutils

## References

### Books
- [SICM 2nd Edition](https://mitpress.mit.edu/sites/default/files/titles/content/sicm_edition_2/book.html) (MIT Press)
- [SICP HTML5 Version](https://sarabander.github.io/sicp/) (sarabander)
- [SICM HTML Version](https://tgvaughan.github.io/sicm/) (tgvaughan)

### Lectures
- [MIT 6.946](https://groups.csail.mit.edu/mac/users/gjs/6946/) - Classical Mechanics: A Computational Approach
- [MIT 6.001](https://ocw.mit.edu/courses/6-001-structure-and-interpretation-of-computer-programs-spring-2005/) - SICP Lectures

### Community
- [Road to Reality](https://roadtoreality.substack.com/) - Sam Ritchie Newsletter
- [mentat-collective](https://github.com/mentat-collective) - Emmy and related projects

## License

- Original SICP/SICM/FDG books: CC BY-NC-SA 3.0 or respective licenses
- Emmy: MIT License
- Personal notes: MIT License

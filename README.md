# SICM Study - Internalization of Flexible Design

[![한국어](https://img.shields.io/badge/lang-한국어-blue)](README-KO.md)

> "Programming is not just a tool, but a **means of verifying understanding**."
> — Gerald Jay Sussman & Jack Wisdom, SICM Preface

> "Rather than explaining through analogy, we build up mathematical content from the beginning, step by step, to reach our conclusions."
> — Roger Penrose, *The Road to Reality*

> "Implementation is no longer the problem. Orchestration is possible too. What remains is **the internalization of flexible design**."
> — Personal reflection on the age of AI agents

## Why This Repository?

In the age of AI agents, **implementation itself is no longer the bottleneck**. Agents can write code, orchestrate complex workflows, and even reason about systems. But there's something they cannot simply download: **the deep intuition for flexible design**.

This repository is a learning space for **internalizing the design principles** that make software adaptable, extensible, and resilient to change. It traces the intellectual lineage from computational thinking through physics to the art of building systems that can evolve.

The name is *sicm-study*, but SICM is just the starting point.
For ultimate goals and philosophical background, see [VISION.md](VISION.md).

## Intellectual Lineage

```
                        ┌─────────────────────────────────────┐
                        │         SUSSMAN'S UNIVERSE          │
                        └─────────────────────────────────────┘

  ┌─────────────────────────────────────────────────────────────────────────┐
  │  COMPUTATIONAL THINKING                 FLEXIBLE DESIGN                 │
  │                                                                         │
  │  SICP (1985)                            SDF (2021)                      │
  │  Structure and Interpretation           Software Design for Flexibility │
  │  of Computer Programs                   "Additive Programming"          │
  │  "Programs = Mathematical Expressions"  "Systems that evolve"           │
  │       │                                      │                          │
  └───────┼──────────────────────────────────────┼──────────────────────────┘
          │                                      │
          ▼                                      ▼
  ┌─────────────────────────────────────────────────────────────────────────┐
  │  PHYSICS AS CODE                                                        │
  │                                                                         │
  │  SICM (2001)                 FDG (2013)                                 │
  │  Classical Mechanics         Differential Geometry                      │
  │  Lagrangian/Hamiltonian      The path to General Relativity            │
  │  "Formulas = Code"           "Geometry = Computation"                   │
  │       │                           │                                     │
  │       └───────────┬───────────────┘                                     │
  │                   ▼                                                     │
  │  Emmy (2020~)     Clojure reimplementation                              │
  │                   Browser + Visualization + Modern ecosystem            │
  └─────────────────────────────────────────────────────────────────────────┘

  ┌─────────────────────────────────────────────────────────────────────────┐
  │  PHYSICS FOUNDATIONS                                                    │
  │                                                                         │
  │  Susskind's Theoretical Minimum                                         │
  │  Classical Mechanics → Quantum → GR                                     │
  │  "Just what you need to proceed to the next level"                      │
  └─────────────────────────────────────────────────────────────────────────┘
```

### Why This Lineage?

The "constructionist learning" that started with Seymour Papert's Logo extends through Gerald Sussman to the core of physics. The idea that *formulas and code are identical* as mathematical tools — this is the foundation of *Universal Science*.

**SDF** adds a crucial dimension: how to build systems that can **evolve** without being rewritten. In the age of AI agents, this is not just good practice—it's the **differentiator** between systems that thrive and systems that become legacy.

### The Core Insight: Additive Programming

From SDF's central thesis:

> **Additive programming** is a strategy for building large systems that can be easily adapted to new situations by adding new code rather than modifying existing, working code.

Key techniques:
- **Generic Procedures**: Dynamic dispatch for extensibility
- **Combinators**: Composing behaviors without modification
- **Propagators**: Decentralized computation models
- **Separation of Generators and Testers**: Independent evolution

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
├── sicp/                    # Computational Thinking
│   ├── book/                # sicp.org (complete book, Babel executable)
│   └── info/                # Emacs info version
│
├── sicm/                    # Classical Mechanics (Sussman & Wisdom)
│   ├── book/                # 9 chapters (org-mode)
│   └── my-solutions/        # Personal solutions
│
├── fdg/                     # Functional Differential Geometry
│   └── book/                # Scheme/Clojure implementations
│
├── sdf/                     # Software Design for Flexibility (NEW)
│   ├── book/                # Full book (org-mode, gitignored)
│   └── README.md            # Core concepts summary
│
├── susskind/                # Theoretical Minimum Series
│   ├── book/                # Classical Mechanics (org-mode, gitignored)
│   └── lecture-*-깊이탐구.org  # Deep study notes (Korean)
│
├── foundations/             # Mathematical Foundations
│   ├── calculus/
│   ├── linear-algebra/
│   ├── differential-geometry/
│   └── variational-principles/
│
├── tools/                   # Development environment
│   └── scheme/              # MIT Scheme setup
│
├── README.md                # This file
├── VISION.md                # Philosophical background
├── CREDITS.md               # Original author acknowledgments
└── AGENTS.md                # AI agent instructions
```

**Note**: `book/` folders contain org-mode conversions of original texts. They are gitignored to respect copyright. The focus is on **study notes and personal understanding**, not redistribution.

## Learning Roadmap

### Track A: Physics as Code (SICM Path)

**Phase 0: Foundations**
- [ ] SICP Chapter 1-2: Procedures, Data Abstraction
- [ ] Susskind Lecture 1-3: Nature of Classical Physics, Motion, Dynamics

**Phase 1: Classical Mechanics**
- [ ] SICM Chapter 1: Lagrangian Mechanics
- [ ] SICM Chapter 3: Hamiltonian Mechanics
- [ ] Susskind Lectures 4-11: Energy, Least Action, Symmetries

**Phase 2: Geometry**
- [ ] FDG: Differential geometry basics
- [ ] Path to General Relativity

### Track B: Flexible Design (SDF Path)

**Phase 0: Design Principles**
- [ ] SDF Chapter 1: Flexibility in Programs
- [ ] SDF Chapter 2: Domain-Specific Languages

**Phase 1: Core Techniques**
- [ ] SDF Chapter 3: Variations on a Scheme
- [ ] SDF Chapter 4: Pattern Matching
- [ ] SDF Chapter 5: Evaluation

**Phase 2: Advanced Patterns**
- [ ] SDF Chapter 6: Layering
- [ ] SDF Chapter 7: Propagation

### Convergence: The Art of Extensible Systems

Both tracks lead to the same insight: **well-designed systems are those that can evolve**. Physics teaches us to find invariants; SDF teaches us to build around them.

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
- [SICP](https://sarabander.github.io/sicp/) - Structure and Interpretation of Computer Programs
- [SICM](https://tgvaughan.github.io/sicm/) - Structure and Interpretation of Classical Mechanics
- [SDF](https://mitpress.mit.edu/9780262045490/) - Software Design for Flexibility (MIT Press, 2021)
- [The Theoretical Minimum](https://theoreticalminimum.com/) - Susskind's lecture series

### Lectures
- [MIT 6.946](https://groups.csail.mit.edu/mac/users/gjs/6946/) - Classical Mechanics: A Computational Approach
- [Stanford Continuing Studies](https://theoreticalminimum.com/courses) - Susskind's Physics Courses

### Community
- [Road to Reality](https://roadtoreality.substack.com/) - Sam Ritchie Newsletter
- [mentat-collective](https://github.com/mentat-collective) - Emmy and related projects

## License

- Original SICP/SICM/FDG books: CC BY-NC-SA 3.0 or respective licenses
- Emmy: MIT License
- Personal notes: MIT License

# phd-dissertation
This repository contains the full text of my PhD dissertation titled "Improving Compiler Construction Using Formal Methods",
completed at The Universoty of Utah in Spring 2021.

My research was advised by Prof. John Regehr, with co-advisors Prof. Mary Hall, Prof. Eric Eide, Prof. Matthew Flatt, and Prof. Nuno Lopes.

## Abstract
Programming languages are becoming more high-level and processors are moving to-
wards more specialization. This trend has increased the gap between high-level program-
ming languages and low-level processors. It is the responsibility of a compiler to bridge the
gap between the two. The key contribution of this dissertation is to use formal techniques
to build parts of the compiler to make them more effective and more correct.
Static analyses compute properties of programs that are true in all executions. Com-
pilers use these properties to justify optimizations such as dead code elimination. Each
static analysis in a compiler should be as precise as possible while remaining sound and
being suﬀiciently fast. Unsound static analyses typically lead to miscompilations, whereas
imprecisions typically lead to missed optimizations. Neither kind of bug is easy to track
down. My contributions include a collection of algorithms that use an Satisfiability Modulo
Theories (SMT) solver to compute sound and maximally precise static analysis results for
fragments of code in the LLVM intermediate representation, enabling automated testing
of the corresponding static analysis code in LLVM. Some of the abstract domains that we
target have convenient properties enabling eﬀicient search for the most precise result, but
one of them (integer ranges) appears to lack these properties; in this case we compute
the most precise result using a CEGIS (Counterexample Guided Inductive Synthesis) loop.
Our test cases include all of the LLVM IR generated while compiling SPEC CPU 2017. I
found many imprecisions, some of which have resulted in patches being made to the LLVM
compiler. My work is important because the correctness and eﬀiciency of a large amount
of real-world code in a number of programming languages depends on the soundness and
precision of static analyses in LLVM.
Peephole optimizations are hard to get right as they involve many corner cases. They
are hard to extend because developers are not using domain specific language to define
the rewrite rules, automatically generate and verify them for soundness. My contributions
include designing an automatic peephole optimizer that is driven by a superoptimizer. It
makes use of a superoptimizer’s intermediate representation to define the peepholes and
transform them to another IR and it guarantees correctness as these optimizations are
verified by a SMT solver.

## Keywords
Formal Methods, Compiler Verification, Static Analysis, LLVM, SMT Solvers, Superoptimization, Program Analysis, Peephole Optimization, Compiler Construction, Optimization Correctness, Domain-Specific Languages, Compiler Testing, Intermediate Representations, Soundness, Precision

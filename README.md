## Typed Named Tensors — companion notebook
Companion to: A Typed Named Tensor Notation for Deep Learning.

This notebook is the executable counterpart to the paper. It walks through the type discipline of §2–§3 cell by cell, builds the framework as Python, and ends with the §3.4 worked example: the type checker rejecting the documented BatchNorm-information-leak bug from MoCo and accepting each of the three canonical fixes.

What you'll see (and run):

The sort algebra (§2) — twelve sorts encoding what each tensor axis is for
Refinement subsorts (§2.5) — narrowing legality via a partial order
The legality table (§2.3) — eight elementary operations × twelve sorts, derived from the axioms
Typed named tensors (§3) — sorted axes plus a NumPy backend
Primitive operations — contract, reduce, normalize, concat, attention, each with type checking
Basic type-checking sanity tests
The §3.4 MoCo worked example as a runnable narrative
A small Transformer-block sketch (§6.1) as an integration test
Reading mode. Each section has prose first, then code. Run cells in order. The whole notebook executes in well under a second on any modern laptop — the type-checking step itself is microseconds; everything else is light NumPy.

Honest limits. This is a proof-of-concept reference implementation (~530 lines), not a competitor to PyTorch. There is no autodiff (the backward pass is proved on paper, not run); no GPU; the operation set covers what's needed to demonstrate the type discipline, not what's needed to train a real model. The point is decidability and concrete bug-catching.

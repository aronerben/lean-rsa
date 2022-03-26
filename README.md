# Proof
This repository contains the proof that RSA encryption undoes decryption as originally described in the [RSA paper](https://people.csail.mit.edu/rivest/Rsapaper.pdf). The proof can be extended to show that decryption undoes encryption.

It makes use of various tactic combinators and often switches between Lean's `MOD` form found in `data.nat.modeq` and the modulo operator equivalence notation to be able to apply appropriate lemmas.

The majority of LOC is used to prove RSA works even in edge-cases (e.g. where a message is not coprime to the product of the two primes). I believe the proof could be shortened a little by utilizing `mathlib` to a greater extent and using clever meta tactics to extract common parts.

The `simp` tactic is never given a list of theorems to use. This means that this proof might not work in all versions of `mathlib`, as new theorems could be marked with the `[simp]` attribute, effectively altering `simp`s behavior in some cases.

The axiom of choice is brought in by various lemmas used throughout the proof.

# Funding
This proof was written as an exercise to learn Lean in the scope of a project currently lead and funded by Damian Kozbur at the University of Zurich, Department of Economics.

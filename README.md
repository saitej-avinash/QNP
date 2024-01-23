# LQafny

LQafny is a language for Qafny. It provides a Markov-decision-process-based small-step quantum operational semantics.

## Overview

Quantum programs are typically described as denotational semantics, e.g., unitary semantics and density matrix semantics, which provides a holistic view of all program probabilistic and nondeterministic behaviors. Locality, the ability of focusing on a single path of nondeterministic choices and a program piece, is essential in analyzing program behaviors, which the denotational semantics lack of.
We develop the LQafny system, admitting small-step operational semantics for quantum programs, inspired by Markov decision process, which permits the locality property.
We also show that the correctness of compiling LQafny to a quantum circuit, admitting denotational semantics.

## Setup

To compile LQafny, you will need [Coq](https://coq.inria.fr/) and [QuickChick](https://github.com/QuickChick/QuickChick). We strongly recommend using [opam](https://opam.ocaml.org/doc/Install.html) to install Coq and `opam switch` to manage Coq versions. We currently support Coq **versions 8.13**.

Assuming you have opam installed (following the instructions in the link above), follow the steps below to set up your environment.
```
# environment setup
opam init
eval $(opam env)

# install some version of the OCaml compiler in a switch named "qnp"
opam switch create qnp 4.12.0
eval $(opam env)

# install Coq -- this will take a while!
opam install coq

# install coq-quickchick
opam install coq-quickchick
```

*Notes*:
* Depending on your system, you may need to replace 4.12.0 in the instructions above with something like "ocaml-base-compiler.4.12.0". Any recent version of OCaml should be fine. 
* We require Coq version >= 8.12. We have tested compilation with 8.12.2, 8.13.2, and 8.14.0.
* opam error messages and warnings are typically informative, so if you run into trouble then make sure you read the console output.

## Compiling & Running LQafny

Run `make` in the top-level directory to compile our Coq proofs. externals directory contains the coq files from SQIR and QWIRE that support the development of LQafny.

## Directory Contents

* QafnySyntax.v - The LQafny language syntax.
* LocusDef.v - Locus and state syntax and equation rules.
* LocusType.v - The LQafny Type system.
* LocusSem.v - The LQafny language semantics.
* LocusTypeProof.v - The LQafny Type system Soundness Proof.
* QafnySQIR.v - The LQafny to SQIR compilation.



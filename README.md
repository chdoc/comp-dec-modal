# Completeness and Decidability of Modal Logic Calculi

[![Travis][travis-shield]][travis-link]
[![Contributing][contributing-shield]][contributing-link]
[![Code of Conduct][conduct-shield]][conduct-link]
[![Zulip][zulip-shield]][zulip-link]
[![coqdoc][coqdoc-shield]][coqdoc-link]
[![DOI][doi-shield]][doi-link]

[travis-shield]: https://travis-ci.com/coq-community/comp-dec-modal.svg?branch=master
[travis-link]: https://travis-ci.com/coq-community/comp-dec-modal/builds

[contributing-shield]: https://img.shields.io/badge/contributions-welcome-%23f7931e.svg
[contributing-link]: https://github.com/coq-community/manifesto/blob/master/CONTRIBUTING.md

[conduct-shield]: https://img.shields.io/badge/%E2%9D%A4-code%20of%20conduct-%23f15a24.svg
[conduct-link]: https://github.com/coq-community/manifesto/blob/master/CODE_OF_CONDUCT.md

[zulip-shield]: https://img.shields.io/badge/chat-on%20zulip-%23c1272d.svg
[zulip-link]: https://coq.zulipchat.com/#narrow/stream/237663-coq-community-devs.20.26.20users

[coqdoc-shield]: https://img.shields.io/badge/docs-coqdoc-blue.svg
[coqdoc-link]: https://coq-community.org/comp-dec-modal

[doi-shield]: https://zenodo.org/badge/DOI/doi:10.22028/D291-26649.svg
[doi-link]: https://doi.org/doi:10.22028/D291-26649

Machine-checked constructive proofs of soundness and completeness
for Hilbert axiomatizations and sequent calculi for the logics K,
K*, CTL, as well as the axiomatizations of PDL, with and without
converse.

## Meta

- Author(s):
  - Christian Doczkal (initial)
- Coq-community maintainer(s):
  - Christian Doczkal ([**@chdoc**](https://github.com/chdoc))
- License: [CeCILL-B](LICENSE)
- Compatible Coq versions: 8.10 or later
- Additional dependencies:
  - [MathComp](https://math-comp.github.io) 1.9.0 or later (`ssreflect` suffices)
- Coq namespace: `CompDecModal`
- Related publication(s):
  - [A Machine-Checked Constructive Metatheory of Computation Tree Logic](https://www.ps.uni-saarland.de/static/doczkal-diss/index.php) doi:[doi:10.22028/D291-26649](https://doi.org/doi:10.22028/D291-26649)
  - [Completeness and decidability of converse PDL in the constructive type theory of Coq](https://hal.archives-ouvertes.fr/hal-01646782/) doi:[https://doi.org/10.1145/3167088](https://doi.org/https://doi.org/10.1145/3167088)

## Building and installation instructions

The easiest way to install the latest released version of Completeness and Decidability of Modal Logic Calculi
is via [OPAM](https://opam.ocaml.org/doc/Install.html):

```shell
opam repo add coq-released https://coq.inria.fr/opam/released
opam install coq-comp-dec-modal
```

To instead build and install manually, do:

``` shell
git clone https://github.com/coq-community/comp-dec-modal.git
cd comp-dec-modal
make   # or make -j <number-of-cores-on-your-machine> 
make install
```


## Documentation

The developments for the individual logics are described in the
publications listed above. The developments on K, K*, and CTL are
described in the author's PhD thesis titled "A Machine-Checked
Constructive Metatheory of Computation Tree Logic". The developments
on PDL and PDL with converse are described in the CPP'18 paper.

### Structure

- The directory `libs` contains infrastructure shared between the
  developments. This includes:
  - `fset.v`: a library for finite sets over types with a choice operator (a precursor of [finmap](https://github.com/math-comp/finmap)).
  - `fset_tac.v`: rudimentary automation for the above (originally implemented by [Alexander Anisimov](https://www.ps.uni-saarland.de/~anisimov/bachelor.php)).
  - `modular_hilbert.v`: a library for constructing proofs in Hilbert axiomatizations for modal logics.
  - `sltype.v`: generic lemmas for alpha/beta decomposition of modal-logic formulas.
- the remaining directories contain the formalizations for the respective logics.
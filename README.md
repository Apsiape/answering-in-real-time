# The work cost of answering in real time

Seth Douglas and Nidhal Mghirbi — October 2026.

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23310628.svg)](https://doi.org/10.5281/zenodo.23310628)

[Read the manuscript](paper/main.pdf) · [TeX source](paper/main.tex) ·
[Machine checks](verification/README.md)

A short letter summarizing all four papers is *Order, not speed: the work price of letting go* ([doi:10.5281/zenodo.23323808](https://doi.org/10.5281/zenodo.23323808); [Apsiape/order-not-speed](https://github.com/Apsiape/order-not-speed)).

Many devices must answer each request before the next one arrives, while remembering what came before. This
paper determines how much work such a device must spend per episode, one complete run of the process, for every finite interactive quantum process whose
outputs carry the same Hamiltonians as its inputs, at every positive finite temperature.

- **Work law for processes.** The least work per episode is kT ln 2 times one quantity: an entropy change plus an
  energy change, both measured against the same adaptive observer, the most demanding one, and minimized over all ways to
  build the process in the order its outputs are due. For processes that commute with time translation, a strong
  converse holds for devices with thermal hardware and a sharp battery.
- **What is free.** A process costs nothing exactly when it is a limit of devices that run energy-conserving steps,
  in the required order, on one shared heat bath.
- **Order costs work.** A two-qubit process that is free when its outputs may wait costs kT ln 2 [1 - h(p)] per
  episode when they may not, where p is the bias of a coin the process draws, even when everything is classical.
- **Without time covariance.** The same law holds for every finite process when the device's whole controller need
  only come back approximately, with its actual mean energy and entropy refunded and its startup capital declared.

All rates here are optimal asymptotic work rates at vanishing error over the complete interaction, with hardware
allowed to grow; where a controller comes back only approximately, its actual mean energy and entropy are also
refunded up to sublinear changes.

This repository contains the manuscript, its source, and the machine checks that accompany it. It is version 1.0.2 ([doi:10.5281/zenodo.23323045](https://doi.org/10.5281/zenodo.23323045)) of the Zenodo record [doi:10.5281/zenodo.23310628](https://doi.org/10.5281/zenodo.23310628); that concept DOI always resolves to the latest version. Version 1.0.1 is [doi:10.5281/zenodo.23310737](https://doi.org/10.5281/zenodo.23310737) and version 1.0.0 is [doi:10.5281/zenodo.23310629](https://doi.org/10.5281/zenodo.23310629). The manuscript is the
authority for exact statements and hypotheses; [verification/README.md](verification/README.md) lists what is checked
by machine and what is proved only in the text.

## Reproduce

Requires Python 3.10+ with the packages in [verification/requirements.txt](verification/requirements.txt), a TeX
distribution with the packages listed in paper/main.tex, and, for the formal proofs, Lean 4 with Mathlib as described
in [verification/README.md](verification/README.md).

    python -m pip install -r verification/requirements.txt
    python paper/build.py
    python verification/run_all.py

The build refuses to finish on any undefined reference or citation, duplicate label or overfull line. Each check
prints what it verifies and exits with status 0 when it passes.
Until Mathlib is set up as described there, the Lean step reports that it was skipped and the run
fails; the Python checks do not need it.

## Companions

This paper is one of four on the thermodynamics of time order, each with its own repository:
- [Only quantum channels save work by waiting](https://github.com/Apsiape/save-work-by-waiting) · [doi:10.5281/zenodo.23310624](https://doi.org/10.5281/zenodo.23310624)
- [The price of keeping time](https://github.com/Apsiape/price-of-keeping-time) · [doi:10.5281/zenodo.23310632](https://doi.org/10.5281/zenodo.23310632)
- [The price of time order](https://github.com/Apsiape/price-of-time-order) · [doi:10.5281/zenodo.23310622](https://doi.org/10.5281/zenodo.23310622)

Earlier papers it builds on are listed, with the exact results used and where, in the appendix "Results from the
companion papers" of the manuscript.

## Reading guide

For the organizing principle, read the introduction, Figure 1 and Table 2 of *The price of time order*. For the device model,
the law for repeated channels and the free set, read *Only quantum channels save work by waiting*. For processes with
memory and the classical example of an order cost, read *The work cost of answering in real time*. For returned
clocks, the batch law and the time reverse, read *The price of keeping time*. Readers following proofs should note that
the finite-source module of *The work cost of answering in real time* (Appendix E, Lemma 12) is established
independently of the channel results it helps to prove.

## License and citation

The manuscript and repository content are available under **CC BY 4.0**. The software and machine-readable
verification artifacts are additionally available under the **MIT License**, at your option; see
[RIGHTS.md](RIGHTS.md) for the scope. [CITATION.cff](CITATION.cff) provides machine-readable citation metadata. Please cite the manuscript by its concept DOI, [10.5281/zenodo.23310628](https://doi.org/10.5281/zenodo.23310628).

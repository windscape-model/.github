# windscape-model

This organization hosts open-source numerical models for the phase-resolved
simulation of turbulent airflow over ocean surface waves. In the atmospheric
models (WRF-WAVE, ERF-WAVE) the sea surface enters the large-eddy simulation as
a moving lower boundary that follows the wave motion, so that the pressure
exerted by the airflow on individual wave crests and troughs is resolved rather
than parameterized. The wave field is either prescribed (WRF-WAVE, ERF-WAVE) or
computed by a coupled wave model (WindSCAPE). The surface wave model (CRESCENT)
uses the high-order spectral method with domain nesting capabilities.

| Repository | Model | Built on | Language | License |
| --- | --- | --- | --- | --- |
| [WRF-WAVE](https://github.com/windscape-model/WRF-WAVE) | Weather Research and Forecasting (WRF) model, version 3.8.1, with a moving bottom boundary that resolves the phase of propagating surface waves | WRF v3.8.1 | Fortran | BSD 3-Clause |
| [ERF-WAVE](https://github.com/windscape-model/ERF-WAVE) | Fork of the Energy Research and Forecasting (ERF) model with a moving bottom boundary and wave phase-resolved capability; the atmospheric component of WindSCAPE | [erf-model/ERF](https://github.com/erf-model/ERF), AMReX | C++ | BSD 3-Clause |
| [CRESCENT](https://github.com/windscape-model/CRESCENT) | Block-structured, adaptive-mesh framework for the simulation of ocean surface waves with the high-order spectral method | AMReX | C++ | BSD 3-Clause |
| [WindSCAPE](https://github.com/windscape-model/WindSCAPE) | Coupled atmosphere-wave model in which ERF-WAVE and CRESCENT run as peers within a single executable | ERF-WAVE, CRESCENT, AMReX | C++ | BSD 3-Clause |

## Relation between the codes

WRF-WAVE is a self-contained model: the moving-wave boundary condition is
implemented within the WRF dynamical core, and the wave field is prescribed.
ERF-WAVE, CRESCENT and WindSCAPE form a modular family built on the AMReX
framework. ERF-WAVE computes the atmospheric flow, CRESCENT computes the
evolution of the wave field, and WindSCAPE couples the two within one
executable, so that the atmosphere and the waves are advanced together.

## Citation and license

Each repository lists the publications that describe its methods and carries
its LICENSE file.

## Contact

Tianyi Li, [tianyili1993@gmail.com](mailto:tianyili1993@gmail.com)

# Batch Connect - CHPC MATLAB

![GitHub Release](https://img.shields.io/github/release/osc/bc_osc_matlab.svg)
[![GitHub License](https://img.shields.io/badge/license-MIT-green.svg)](https://opensource.org/licenses/MIT)

A Batch Connect app designed for Open OnDemand that launches MATLAB on a CHPC infrastructure.

Most content below is from the original [OSC app](https://github.com/OSC/bc_osc_matlab).

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [MATLAB] R2016b+
- [Xfce Desktop] 4+

For VNC server support:

- [TurboVNC] 2.1+
- [websockify] 0.8.0+

For hardware rendering support (not on CHPC):

- [X server] (CHPC does not run X server on compute nodes)
- [VirtualGL] 2.3+

**Optional** software:

- [Lmod] 6.0.1+ or any other `module purge` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job

[MATLAB]: https://www.mathworks.com/
[Xfce Desktop]: https://xfce.org/
[TurboVNC]: http://www.turbovnc.org/
[websockify]: https://github.com/novnc/websockify
[X server]: https://www.x.org/
[VirtualGL]: http://www.virtualgl.org/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod

## Install

git clone and modify for your needs.

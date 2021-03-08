# Batch Connect - CHPC COMSOL Multiphysics

A Batch Connect app designed for Open OnDemand that launches COMSOL Multiphysics
on CHPC infrastructure.

Most content below is from the original [OSC app](https://github.com/OSC/bc_osc_comsol).

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [COMSOL Multiphysics] 5.1+
- [Xfce Desktop] 4+

For VNC server support:

- [TurboVNC] 2.1+
- [websockify] 0.8.0+

For hardware rendering support:

- [X server]
- [VirtualGL] 2.3+

**Optional** software:

- [Lmod] 6.0.1+ or any other `module purge` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job

[COMSOL Multiphysics]: https://www.comsol.com
[Xfce Desktop]: https://xfce.org/
[TurboVNC]: http://www.turbovnc.org/
[websockify]: https://github.com/novnc/websockify
[X server]: https://www.x.org/
[VirtualGL]: http://www.virtualgl.org/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod

## Install

git clone and modify to your needs

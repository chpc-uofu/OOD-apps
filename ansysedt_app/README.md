# Batch Connect - CHPC ANSYS Electronic Desktop

A Batch Connect app designed for Open OnDemand that launches an ANSYS EDT on CHPC infrastructure.

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [ANSYS Electronics Desktop] 
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

[ANSYS Electronics Desktop]: https://www.ansys.com/products/electronics/ansys-electronics-desktop
[CFX]: https://www.ansys.com/Products/Fluids/ANSYS-CFX
[Fluent]: https://www.ansys.com/Products/Fluids/ANSYS-FLUENT
[Xfce Desktop]: https://xfce.org/
[TurboVNC]: http://www.turbovnc.org/
[websockify]: https://github.com/novnc/websockify
[X server]: https://www.x.org/
[VirtualGL]: http://www.virtualgl.org/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod

## Install
git clone and modify to your needs. Note that ```template/script.sh.erb``` is set to run only on a single node, some of the commented content sets up multi-node parallel run but is disabled. 

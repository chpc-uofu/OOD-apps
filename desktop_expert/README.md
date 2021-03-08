# Batch Connect - Expert Desktop

A Batch Connect app designed to launch a GUI desktop withing a batch job. Expert versions has more options to request resources.

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node).

One of the following desktops:

- [Xfce Desktop] 4+
- [Mate Desktop] 1+ (*default*)
- [Gnome Desktop] 2 (currently we do not support Gnome 3)

For VNC server support:

- [TurboVNC] 2.1+
- [websockify] 0.8.0+

For hardware rendering support:

- [X server]
- [VirtualGL] 2.3+

[Xfce Desktop]: https://xfce.org/
[Mate Desktop]: https://mate-desktop.org/
[Gnome Desktop]: https://www.gnome.org/
[TurboVNC]: http://www.turbovnc.org/
[websockify]: https://github.com/novnc/websockify
[X server]: https://www.x.org/
[VirtualGL]: http://www.virtualgl.org/

## Install

git clone and modify to your needs.

## Configuration

Please see the [Install Desktops] section in the [Open OnDemand Documentation]
to learn more about setting up and configuring a desktop at your HPC center.

[Install Desktops]: https://osc.github.io/ood-documentation/master/enable-desktops.html
[Open OnDemand Documentation]: https://osc.github.io/ood-documentation/master/index.html


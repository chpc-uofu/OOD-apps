# Batch Connect - CHPC Jupyter Lab

An interactive app designed for Open OnDemand that launches a Jupyter Lab
server on CHPC infrastructure.

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [Lmod] 6.0.1+ or any other `module purge` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job before
  launching the Jupyter server.
- [Jupyter] 4.2.3+ (earlier versions are untested but may work for
  you)
- [OpenSSL] 1.0.1+ (used to hash the Jupyter server password)

[Jupyter]: https://jupyter.org/
[OpenSSL]: https://www.openssl.org/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod

## Install

git clone and modify to your needs.

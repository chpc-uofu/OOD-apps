# [WIP] Batch Connect - CHPC Example Shiny App

A Batch Connect app designed for Open OnDemand that launches a Shiny App on 
CHPC clusters.

## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [Shiny] x.y.z+
- [Lmod] 6.0.1+ or any other `module purge` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job

[Shiny]: https://shiny.rstudio.com/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod

## Install

git clone and modify for your needs.

# Batch Connect - OSC RStudio Server


An interactive app designed for OSC OnDemand that launches an RStudio Server
within on CHPC infrastructure.

As of Mar21, RStudio Server >= 1.4 has made authentication changes that don't work with OOD. One has to pull the Docker containers that are still using RStudio Server 1.3.x. To use 1.3.x, there is also a small modification needed in ```template/bin/auth```.

As of Mar20 we are using Docker containers from rocker and bioconductor:
- base R image, based on [https://hub.docker.com/r/rocker/rstudio](https://hub.docker.com/r/rocker/rstudio)
- geospatial R image, based on [https://hub.docker.com/r/rocker/geospatial](https://hub.docker.com/r/rocker/geospatial) - this has installed gdal and rgdal, among other things.
- bioinfomatics R image, based on [https://hub.docker.com/r/bioconductor/bioconductor_docker](https://hub.docker.com/r/bioconductor/bioconductor_docker) - this has installed most if not all bioconductor system dependencies, like hdf5, udunits, gdal, ... Therefore user based R library installations should work as these system based dependencies are present.

We build the container images and store them locally as e.g. ```singularity build ood-rstudio-rocker_3.6.2.sif docker://rocker/rstudio```. In the [environment modules](https://github.com/CHPC-UofU/bc_osc_rstudio_server/tree/master/modulefiles), we define paths to these containers, and also environment variables that set things like the user R libraries and environment file location, and the OOD's helper variables used in ```template/script.sh.erb```.

Stuff below is deprecated now - the rocker and bioconductor based Docker images work without need to hand modify the container

As of Nov19 using Virginia Tech's R containers, as compared to previously used OSC's. The main reason for this is that VT includes some commonly used R packages in the container so users don't have to install them, and, they have different containers for different needs (Bioinformatics, Geospatial).

The containers are at: [https://hub.docker.com/u/rsettlag](https://hub.docker.com/u/rsettlag)  
VT's OOD apps are at: [https://github.com/rsettlage/ondemand2](https://github.com/rsettlage/ondemand2)

Due to a few hard coded pieces we hand edit the containers as follows:  
```
$ singularity build --sandbox ood-rstudio-bio_3.6.1 docker://rsettlag/ood-rstudio-bio:3.6.1  
sudo singularity shell --writable ood-rstudio-bio_3.6.1  
apt-get update && apt-get install apt-file -y && apt-file update && apt-get install vim -y  
vi /usr/local/lib/R/etc/Rprofile.site  
```
- remove:  
```
 Sys.setenv(http_proxy="http://uaserve.cc.vt.edu:8080")  
 Sys.setenv(https_proxy="http://uaserve.cc.vt.edu:8080")  
 Sys.setenv(R_ENVIRON_USER="~/.Renviron.OOD")  
 Sys.setenv(R_LIBS_USER="~/R/OOD/3.6.1")  

$ sudo singularity build ood-rstudio-bio_3.6.1.sif ood-rstudio-bio_3.6.1/  
```


## Prerequisites

This Batch Connect app requires the following software be installed on the
**compute nodes** that the batch job is intended to run on (**NOT** the
OnDemand node):

- [Lmod] 6.0.1+ or any other `module restore` and `module load <modules>` based
  CLI used to load appropriate environments within the batch job before
  launching the RStudio Server.

**without Singularity**

- [R] 3.3.2+ (earlier versions are untested but may work for you)
- [RStudio Server] above 1.0.136 and below 1.4 (1.4 added an extra authentication part which is hard to incorporate to Open OnDemand)
- [PRoot] 5.1.0+ (used to setup fake bind mount)

**or with Singularity**

- [Singularity] 2.4.2+
- A Singularity image similar to [nickjer/singularity-rstudio]
- Corresponding module to launch the above Singularity image (see
  [example_module])

[R]: https://www.r-project.org/
[RStudio Server]: https://www.rstudio.com/products/rstudio-server/
[PRoot]: https://proot-me.github.io/
[Singularity]: http://singularity.lbl.gov/
[Lmod]: https://www.tacc.utexas.edu/research-development/tacc-projects/lmod
[nickjer/singularity-rstudio]: https://www.singularity-hub.org/collections/463
[example_module]: https://github.com/nickjer/singularity-rstudio/blob/master/example_module/

## Install

git clone and modify to your needs

build the containers and create module files as in the included examples

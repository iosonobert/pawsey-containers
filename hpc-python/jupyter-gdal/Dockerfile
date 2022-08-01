# OG Hacker https://github.com/IOMRC/docker_stacks/blob/master/python_aodn/Dockerfile

ARG OWNER=jupyter
ARG BASE_CONTAINER=$OWNER/scipy-notebook
FROM $BASE_CONTAINER

LABEL maintainer="Jupyter Project <jupyter@googlegroups.com>"

# Fix: https://github.com/hadolint/hadolint/wiki/DL4006
# Fix: https://github.com/koalaman/shellcheck/wiki/SC3014
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

USER root 

#RUN echo "THE JOYS OF GDAL: https://mothergeo-py.readthedocs.io/en/latest/development/how-to/gdal-ubuntu-pkg.html"
RUN apt update

# This is to enable add-apt-repository [https://itsfoss.com/add-apt-repository-command-not-found/] 
RUN apt-get -y install software-properties-common 
RUN add-apt-repository ppa:ubuntugis/ppa

#RUN bash -c '/bin/echo "GDAL VERSION AVAILABLE"'
#RUN bash -c '/bin/echo -e apt-cache madison gdal-bin'

RUN apt-get -y install gdal-bin

#RUN bash -c '/bin/echo "GDAL VERSION BELOW"'
#RUN bash -c '/bin/echo -e ogrinfo --version'

RUN apt-get -y install libgdal-dev
#
RUN export CPLUS_INCLUDE_PATH=/usr/include/gdal
RUN export C_INCLUDE_PATH=/usr/include/gdal
#
RUN apt-get install -y git

RUN chown 755 /home/jovyan/.cache

USER $NB_USER

RUN pip install \
        GDAL==3.3.2 \
        shapely 
        #cartopy # Cartopy fails

#
## The below also fails
## RUN pip install gdal # 
#
#
#
#RUN chown 755 /home/jovyan/.cache
#
## Install extra python packages for oceanography
## RUN pip install --upgrade --ignore-installed numpy==1.17.4
#
#RUN pip install \
#	# gsw \
#	netcdf4 \
#	xarray \
#    shapely \
#    zarr \
#    git+https://github.com/mrayson/iwaves.git \
#    git+https://github.com/mrayson/sfoda.git \
#    git+https://github.com/mrayson/iwatlas.git \
#    # # GDAL\
#    pyproj
#
## Need the below or the sfoda cython imports don't work
#RUN pip install --upgrade numpy

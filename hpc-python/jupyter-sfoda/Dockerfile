# OG Hacker https://github.com/IOMRC/docker_stacks/blob/master/python_aodn/Dockerfile

ARG OWNER=mrayson
ARG BASE_CONTAINER=$OWNER/jupyter_gdal
FROM $BASE_CONTAINER

LABEL maintainer="Matt Rayson <matt.rayson@gmail.com>"

RUN pip install \
	netcdf4 \
	xarray \
        zarr \
        pyproj \
        cmocean \
        git+https://github.com/mrayson/sfoda.git \
        git+https://github.com/mrayson/iwaves.git \
        git+https://github.com/mrayson/iwatlas.git \
        arviz \
        jaxlib \
        jax \
        jaxopt \
        blackjax \
        pymc \
        emcee \
        corner \
        tqdm \
        gptide

USER $NB_USER



# OG Hacker https://github.com/IOMRC/docker_stacks/blob/master/python_aodn/Dockerfile

ARG OWNER=mrayson
ARG BASE_CONTAINER=$OWNER/jupyter-sfoda
FROM $BASE_CONTAINER

LABEL maintainer="Matt Rayson <matt.rayson@gmail.com>"

USER root 

RUN conda install -c conda-forge swot_simulator

USER $NB_USER



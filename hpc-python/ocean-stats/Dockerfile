# OG Hacker https://github.com/IOMRC/docker_stacks/blob/master/python_aodn/Dockerfile

ARG OWNER=mrayson
ARG BASE_CONTAINER=$OWNER/jupyter-sfoda
FROM $BASE_CONTAINER

LABEL maintainer="Matt Rayson <matt.rayson@gmail.com>"

RUN pip install \
        arviz \
        jaxlib \
        jax \
        jaxopt \
        blackjax \
        pymc \
        emcee \
        corner \
        tqdm \
        cmocean

USER $NB_USER



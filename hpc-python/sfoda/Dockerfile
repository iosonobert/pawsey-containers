#FROM pawsey/hpc-python:3.7_intel2020.2_hdf5mpi_mpich3.1.4
FROM osgeo/gdal

LABEL maintainer="matt.rayson@uwa.edu.au"

RUN apt-get update \
    &&  apt install -y python3-pip \
        git


# Install extra python packages for oceanography
#RUN pip install --upgrade --ignore-installed numpy==1.17.4
RUN pip install --upgrade --ignore-installed numpy==1.20.0
RUN pip install \
	gsw \
	netcdf4 \
	xarray \
        shapely \
        zarr \
        git+https://github.com/mrayson/iwaves.git@v0.5.0 \
	git+https://github.com/mrayson/sfoda.git \
        GDAL\
        pyproj==2.4.1

	#git+https://github.com/mrayson/sfoda.git@v0.0.5 \

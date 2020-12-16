FROM pawsey/hpc-python:3.7_intel2020.2_hdf5mpi_mpich3.1.4

LABEL maintainer="matt.rayson@uwa.edu.au"

# Install extra python packages for oceanography
RUN pip install \
	gsw \
	netcdf4 \
	xarray \
	git+https://github.com/mrayson/iwaves.git@v0.5.0 \
	git+https://github.com/mrayson/sfoda.git@v0.0.5 

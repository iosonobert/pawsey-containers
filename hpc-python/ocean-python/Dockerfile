FROM pawsey/hpc-python:3.7_intel2020.2_hdf5mpi_mpich3.1.4

LABEL maintainer="matt.rayson@uwa.edu.au"



#RUN  apt-get update -qq \
#    && apt-get -y --no-install-recommends install software-properties-common
#    #ppa-purge
#    #\
#    #    gnupg
#
##RUN add-apt-repository ppa:ubuntugis/ppa \
##RUN ppa-purge ppa:ubuntugis/ubuntugis-unstable
#RUN add-apt-repository ppa:ubuntugis/ubuntugis-unstable \
#      && apt-get update -qq 
#

#RUN apt-get update -qq \
#     && apt-get -y --no-install-recommends install \
#        gdal-bin \
#        libgdal-dev 
#        #python3-gdal
#
#ENV CPLUS_INCLUDE_PATH=/usr/include/gdal
#ENV C_INCLUDE_PATH=/usr/include/gdal

#RUN apt-get update
#RUN apt-get install -y software-properties-common && apt-get update
#RUN apt-get install -y python3.7-dev
#RUN add-apt-repository ppa:ubuntugis/ppa &&  apt-get update
#RUN apt-get update -qq \ 
#   && apt-get install -y software-properties-common \
#   && build-essential \
#   && apt-get update -qq
##RUN apt-add-repository ppa:ubuntugis/ubuntugis-unstable &&  apt-get update
#RUN add-apt-repository ppa:ubuntugis/ppa &&  apt-get update
RUN apt-get update -qq \ 
   && apt-get install -y libgdal-dev
ENV CPLUS_INCLUDE_PATH=/usr/include/gdal
ENV C_INCLUDE_PATH=/usr/include/gdal
RUN pip install GDAL==2.4.0


#RUN conda install --no-update-deps -y conda-forge::gdal
# Install extra python packages for oceanography
#RUN pip install  sqlite3
RUN pip install \
	gsw \
	netcdf4 \
	xarray \
        git+https://github.com/mrayson/iwaves.git@v0.5.0 \
	git+https://github.com/mrayson/sfoda.git@v0.0.5 \
        --upgrade numpy \
        dask-mpi \
        sparse \
        emcee \
        pymc3

##Docker run help

Build the docker file locally and push the container to dockerhub

sudo docker build --progress=plain -t mrayson/ocean_stats:latest .

Test it runs

sudo docker run mrayson/ocean_stats:latest python -c "from sfoda.utils import maptools;print('GDAL import OK')"

(It will crash due to not finding a file but should load the libraries fine...)

Push to docker hub

or... convert to singularit and copy directly to pawsey

## Convert to a singularity image

sudo singularity build /pathto/ocean_stats.sif docker-daemon://mrayson/ocean_stats:latest

###sudo docker tag iwaves latest
(optional login: `sudo docker login`)

sudo docker push mrayson/ocean_stats:tagname

pull it down on pawsey:

shifter pull mrayson/ocean_stats

## Docker notes

To change docker image store directory:

https://www.ibm.com/docs/en/cloud-private/3.2.x?topic=pyci-specifying-default-docker-storage-directory-by-using-bind-mount

##Docker run help

Build the docker file locally and push the container to dockerhub

sudo docker build -t mrayson/sfoda:sfoda006 .

Test it runs

sudo docker run mrayson/sfoda:sfoda006 python 

(It will crash due to not finding a file but should load the libraries fine...)

Push to docker hub

or... convert to singularit and copy directly to pawsey

## Convert to a singularity image

singularity build python_sfoda006.sif docker-daemon://mrayson/sfoda:sfoda006

###sudo docker tag iwaves latest
(optional login: `sudo docker login`)

sudo docker push mrayson/ocean_python:tagname

pull it down on pawsey:

shifter pull mrayson/iwaves

## Docker notes

To change docker image store directory:

https://www.ibm.com/docs/en/cloud-private/3.2.x?topic=pyci-specifying-default-docker-storage-directory-by-using-bind-mount

## Running a jupyter notebook on setonix

1. `sbatch <path_to>/start_jupyter.slm <path_for_notebook_home>
2. `tail LOGS/jupyter-<jobid>.out`
3. Copy the line that says `ssh -f -N -l ...`
4. Paste this line into a separate (local) terminal. This will create a *tunnel* to the appropriate port.
5. Open a browser and navigate to `localhost:8888`. Note that the port number 8888 may change if slurm could not find it.
6. You may be asked for a token. This should also be printed in Step 2.
7. Start doing work!


---

## Instructions for building the docker container

**Note that this step is only necessary to build a fresh container on dockerhub. The instructions above work without these steps**

Build the docker file locally and push the container to dockerhub

sudo docker build --progress=plain -t mrayson/jupyter_sfoda:latest .

Test it runs

sudo docker run mrayson/jupyter_sfoda:latest python -c "from sfoda.utils import maptools;print('GDAL import OK')"

(It will crash due to not finding a file but should load the libraries fine...)

Push to docker hub

or... convert to singularit and copy directly to pawsey

## Convert to a singularity image

sudo singularity build /pathto/jupyter_sfoda.sif docker-daemon://mrayson/jupyter_sfoda:latest

###sudo docker tag iwaves latest
(optional login: `sudo docker login`)

sudo docker push mrayson/jupyter_sfoda:tagname

pull it down on pawsey:

shifter pull mrayson/jupyter_sfoda

## Docker notes

To change docker image store directory:

https://www.ibm.com/docs/en/cloud-private/3.2.x?topic=pyci-specifying-default-docker-storage-directory-by-using-bind-mount

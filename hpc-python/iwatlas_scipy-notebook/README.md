# iwaveatlas container using the scipy-notebook base container

**Does not have full gdal functionality**

`pip install gdal` not working due to known issue with gdal 3.0.4 - see issues

## Docker run help

Build locally

CD into this folder `./hpc-python/iwatlas2`

Windows:
`docker build -t iwaveatlas3 ./hpc-python/iwatlas_scipy-notebook`

Test it runs

`/home/jovyan/work`

`docker run -v ./mount:/home/jovyan/work -p 8899:8888 iwaveatlas3`

`docker run -v /c/docker_mounts/iwatlas_scipy-notebook:/home/jovyan/work -p 8899:8888 iwaveatlas3`

Access notebook with the 8899:

Copy the line:

http://127.0.0.1:8888/lab?token=cfa035b978e3e93d488e8b62b4d62c87a5d550494d6591e5

But replace the 8888 with 8899:

http://127.0.0.1:8899/lab?token=cfa035b978e3e93d488e8b62b4d62c87a5d550494d6591e5





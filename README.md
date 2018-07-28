# rpi-jupyter-lab
JupyterLab Server on Raspberry Pi. 
Read more about [Jupyterlab](https://github.com/jupyterlab/jupyterlab)

Your own Jupyter Notebook Server on [Raspberry Pi](https://www.raspberrypi.org).

Despite the fact that we adore Raspberry Pi and it is becoming more and more powerful, it is not intended to run large cpu intensive tasks. It will be slow and the best model only offers 1G of RAM. 

For larger datasets, you either need to use incremental machine learning algorithms or build a cluster and run Spark on it. I am currently working on the latter which would be interesting.

----------
This is a Dockerfile for building __rpi-jupyter-lab__. The image is built on a Raspberry Pi 3 running Hypriot OS](http://blog.hypriot.com/). It is a minimal notebook server with [resin/rpi-raspbian:jessie](https://hub.docker.com/r/resin/rpi-raspbian/) as base image without additional packages.  


### Installing
Go to [Hypriot OS](http://blog.hypriot.com/) and follow the steps to get the Raspberry Pi docker ready. Then, run the following:

    docker pull kidig/rpi-jupyter-lab


### Running in detached mode
    docker run -dp 8888:8888 kidig/rpi-jupyter-lab 

Now you can access your notebook at `http://<docker host IP address>:8888`

### Configuration
If you would like to change some config, create your own jupyter_notebook_config.py on the docker host and run the following:

    docker run -itp <host port>:<dest port> -v <path to your config file>:/root/.jupyter/jupyter_notebook_config.py kidig/rpi-jupyter-lab

This maps a local config file to the container.

The following command gives you a bash session in the running container so you could do more:

    docker exec -it <container id> /bin/bash

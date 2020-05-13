# Docker Environment
Docker allows an easy execution of the provided scripts by creating a virtual environment that installs all the needed dependencies. This folder contains a dockerfile that installs a Python 3.6 environment, TensorFlow, Keras and more.

## Setup
First, install Docker as described in the documentation: https://docs.docker.com/install/

Then, build from the root folder of the repository the docker container. Run:
```
docker build . -t dl4nlp 
```

This builds the Python 3.6 container and assigns the name *dl4nlp* to it. 

Then start the container. On Linux, run:
```
docker run -it -v "$PWD":/src/ dl4nlp bash 
```

On Windows, run:
```
docker run -it -v "%cd%":/src/ dl4nlp bash
```

The $PWD (%cd% on Windows) gets the current path and mounts it in the container to the folder /src. You can also pass other paths on your hosting system that should be used in the container:
```
docker run -it -v /my/path/on/host/system:/src/ dl4nlp bash
```


Using the bash in the container, you can execute python code. For example, run:
```
python my_script.py
```

### Assigning more RAM
In later home exercises, you might run into out of memory errors because the memory limitation for the docker container is too harsh. Refer to https://docs.docker.com/engine/reference/run/#runtime-constraints-on-resources for the command line options to grant Docker more memory.
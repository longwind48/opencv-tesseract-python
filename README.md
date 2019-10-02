# opencv-tesseract-python

This docker build includes the following:

- tesseract-ocr 4.0.0-2 

- python 3.7.4 (with jupyter notebook)

- ghostscript 9.27~dfsg-2+deb10u2 

- opencv 4.1.0



# Setup

Our respository runs on python 3.7.4. We manage our dependencies and runtimes using docker containers. it is advisable to adjust your allocated ram and memory in docker settings. 

**Docker** 

For first time setup, follow the commands to setup the docker container. 

  ```bash
  # Pull docker image
  docker pull longwind48/opencv-tesseract-python-jupyter
  
  # cd to the folder you want to mount
  cd <directory>

  # Start docker container
  docker run --entrypoint "/bin/bash" --volume `pwd`:/workspace/myproject -p 10000:8888 -it longwind48/opencv-tesseract-python-jupyter:latest

  # Start Jupyter notebook
  jupyter lab --port=8888 --ip=0.0.0.0 --allow-root --no-browser .
  ```
For subsequent runs, 

  ```bash
  # Start container
  docker start <CONTAINER_NAME>

  # Enter bash of container
  docker exec -it <CONTAINER_NAME> /bin/bash

  # Start Jupyter notebook
  jupyter lab --port=8888 --ip=0.0.0.0 --allow-root --no-browser .

  ```
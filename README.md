# research-container

This repository contains examples of Dockerfile used for creating docker container. Information of Docker could be found [here](https://en.wikipedia.org/wiki/Docker_(software)).

## Prerequisites

To make use of docker, we need several steps for prerequisites:

1. First **sign up** on [docker.com](https://www.docker.com/get-started), then sign in to the dockerhub.

2. Download [docker desktop](https://hub.docker.com/?overlay=onboarding).

## Prepare an image and push it on dockerhub

Although there is a good tutorial on docker desktop download page, we still make a instruction here base on the tutorial and add several compensations.

### Dockerfile preparation

Write your Dockerfile locally, you could save in on [Github](https://github.com/) (the same as me) or anywhere you want. Examples of Dockerfile could be found in this repository.

### Build a Docker image 

Build your docker image locally by:

```bash
cd <your-Dockerfile-path> &&
docker build -t <TAG> .
```

Please don't loss the last *dot* in the command. I highly recommand that the ```<TAG>``` should be of the form: ```<hub-user>/<repo-name>[:<tag>]```, or you may meet trouble when pushing the image to dockerhub. Default ```<tag>``` name will be **latest**. If you create a docker with 'wrong' tag, change the tag by: 

```bash
docker tag <existing-image> <hub-user>/<repo-name>[:<tag>]
```  

### Push a Docker image

Push the docker image to dockerhub by:

```bash
docker push <hub-user>/<repo-name>[:<tag>]
``` 

### Run a Docker image

You could run the docker image by:

```bash
docker run -it --rm <hub-user>/<repo-name>[:<tag>]
```

The image would automatically pull from dockerhub if the image is not found locally.

### Manage local image

Show a list of local image by:

```bash
docker images
```

delete local image by:

```bash
docker rmi <image id>
```

or

```bash
docker rmi <hub-user>/<repo-name>[:<tag>]
```
# research-container

This is an example of Dockerfile used for creating docker container. Docker is a very easy way to create environment on your computer system.

### Prerequisites

To make use of docker, we need several steps for prerequisites:

1. first **sign up** on [docker.com](https://www.docker.com/get-started), then sign in to the dockerhub.

2. download [docker desktop](https://hub.docker.com/?overlay=onboarding).

### Prepare an image and push it on dockerhub

Although there is a good tutorial on docker desktop download website, we make a instruction here base on the docker tutorial and add several compensations.

##### Dockerfile preparation

Write your Dockerfile on [Github](https://github.com/) or anywhere you want, an example of Dockerfile could be found in this repository.

##### Build a Docker image 

Build your docker image locally by:

```bash
cd <your-Dockerfile-path> &&
docker build -t <TAG> .
```

I highly recommand that the **<TAG>** should be in the form: ```<hub-user>/<repo-name>[:<tag>]```. If you do not do like this, you may meet trouble when push the image. Default ```<tag>``` name will be latest.

If you create a docker with wrong tag, change the tag by: 

```bash
docker tag <existing-image> <hub-user>/<repo-name>[:<tag>]
```  

Test your docker image locally by running:
```bash
docker run <hub-user>/<repo-name>[:<tag>]
```

##### Push a Docker image

Push the docker image by:

```bash
docker push <hub-user>/<repo-name>[:<tag>]
``` 

##### Run a Docker image

You could run the docker image by:

```bash
docker run -it --rm <hub-user>/<repo-name>[:<tag>]
```

The image would automatically pull if the image is not found locally.

##### Manage local image

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
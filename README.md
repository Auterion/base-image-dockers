# base-image-dockers
Base images for Auterion Applications

Source for the base docker images you can used to build Applications for AuterionOS.

You can build the base image of your choice with the following command:

```
docker build -f <path>/Dockerfile <path> --build-arg BASE_IMAGE=arm64v8/ubuntu:focal --build-arg <arg=value> -t <tag>
```

### mavsdk

You can build the base image for arm64 platform with the following command:

```
docker build -f mavsdk/Dockerfile mavsdk --build-arg BASE_IMAGE=arm64v8/ubuntu:focal --build-arg MAVSDK_VERSION=v0.40.0 -t auterion/ubuntu-mavsdk:v0.40.0
```

### python-mavsdk

You can build the base image for arm64 platform with the following command:

```
docker build -f python-mavsdk/Dockerfile python-mavsdk --build-arg BASE_IMAGE=arm64v8/ubuntu:focal --build-arg PYTHON_MAVSDK_VERSION=0.18.0 -t auterion/ubuntu-python-mavsdk:0.18.0
```

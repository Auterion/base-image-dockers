ARG BASE_IMAGE
FROM $BASE_IMAGE

ARG PYTHON_MAVSDK_VERSION=develop

RUN apt update && apt install -y python3 python3-pip \
    && apt clean \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install protobuf jinja2 mavsdk==${PYTHON_MAVSDK_VERSION} --target=/tmp
WORKDIR /install
RUN cp -r /tmp/mavsdk \
    /tmp/aiogrpc \
    /tmp/grpc \
    /tmp/six.py \
    /tmp/google \
    /install
RUN cp -r /install/ /usr/lib/python3/dist-packages/

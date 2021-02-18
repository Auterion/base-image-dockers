FROM amd64/ubuntu as build-stage

ARG DEBIAN_FRONTEND=noninteractive

RUN apt update && \
    apt install -y \
    build-essential \
    git \
    cmake \
    libjsoncpp-dev \
    libcurl4-openssl-dev \
    libtinyxml2-dev \
    debhelper \
    pkg-config \
    && apt clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /buildroot
RUN git clone https://github.com/mavlink/MAVSDK.git -b v0.35.1 --recursive mavsdk
RUN cd mavsdk && \
    ./tools/generate_debian_changelog.sh > debian/changelog && \
	DEB_BUILD_OPTIONS=nocheck dpkg-buildpackage -us -uc -nc -b
RUN dpkg -i /buildroot/libmavsdk*.deb

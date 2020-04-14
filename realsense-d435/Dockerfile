FROM ubuntu:18.04

MAINTAINER genmai99

WORKDIR /realsense

# nvidia-container-runtime
ENV NVIDIA_VISIBLE_DEVICES ${NVIDIA_VISIBLE_DEVICES:-all}
ENV NVIDIA_DRIVER_CAPABILITIES ${NVIDIA_DRIVER_CAPABILITIES:+$NVIDIA_DRIVER_CAPABILITIES,}graphics

# apt-key のエラー対策
# ref https://qiita.com/jacob_327/items/e99ca1cf8167d4c1486d
ENV APT_KEY_DONT_WARN_ON_DANGEROUS_USAGE 1

# git installの時にtzdataで止まる対策
# ref https://qiita.com/yagince/items/deba267f789604643bab
ENV DEBIAN_FRONTEND=noninteractive

RUN apt update && apt install -y gnupg  software-properties-common

# realsense パッケージセットアップ
# https://github.com/IntelRealSense/librealsense/blob/master/doc/distribution_linux.md
RUN apt-key adv --keyserver keys.gnupg.net --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCDE || apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-key F6E65AC044F831AC80A06380C8B3A55A6F3EFCD
RUN add-apt-repository "deb http://realsense-hw-public.s3.amazonaws.com/Debian/apt-repo bionic main" -u


# aptインストール   
RUN apt update && apt install -y \
    libsm6\
    libxext6\
    libxrender-dev\
    cmake\
    ffmpeg \
    libavcodec-dev \
    libavformat-dev \
    libavresample-dev \
    libjpeg-dev \
    libpng-dev \
    libswscale-dev \
    libtbb-dev \
    libtiff-dev \
    libv4l-dev \
    libssl-dev\
    python3-dev\
    python3-pip\
    python-tk\
    cpio \
    git \
    mesa-utils \
    x11-apps \
    librealsense2-dkms \
    librealsense2-utils \
    librealsense2-dev \
    librealsense2-dbg \
    sudo && \
    apt clean

# pipインストール 
RUN pip3 install opencv-python opencv-contrib-python pyrealsense2 imageio scikit-image numpy lxml pillow Cython contextlib2


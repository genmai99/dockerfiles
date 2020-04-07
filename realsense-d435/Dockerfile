FROM ubuntu:18.04

MAINTAINER genmai99

WORKDIR /realsense

# git installの時にtzdataで止まる対策
# ref https://qiita.com/yagince/items/deba267f789604643bab
ENV DEBIAN_FRONTEND=noninteractive

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
    sudo && \
    apt clean

# pipインストール 
RUN pip3 install opencv-python opencv-contrib-python pyrealsense2 imageio scikit-image numpy lxml pillow Cython contextlib2

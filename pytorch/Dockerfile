FROM nvidia/cuda:10.2-cudnn7-devel-ubuntu18.04
MAINTAINER genmai99
WORKDIR /work

# git installの時にtzdataで止まる対策
# ref https://qiita.com/yagince/items/deba267f789604643bab
ENV DEBIAN_FRONTEND=noninteractive

ENV PYTHON_VERSION 3.7.1
ENV TZ=Asia/Tokyo

# update and upgrade
RUN apt update && apt upgrade -y
# Install python3
RUN apt install -y python3-dev python3-pip python-tk
# Install devtool
RUN apt install -y build-essential cmake unzip pkg-config
# Install tools
RUN apt install -y ssh curl git cpio ffmpeg sudo
# Install image lib
RUN apt install -y libjpeg-dev libpng-dev libtiff-dev
# Install video codec
RUN apt install -y libavcodec-dev libavformat-dev libswscale-dev libv4l-dev libxvidcore-dev libx264-dev
# Install opencv
RUN apt update && apt install -y libsm6 libxext6 libxrender-dev libtbb-dev libssl-dev libopencv-dev
# clean
RUN apt clean

# pip update
RUN pip3 install -U pip
# Install opencv
RUN pip3 install opencv-python opencv-contrib-python
# Install dev tools
RUN pip3 install imageio numpy pandas matplotlib scikit-image lxml pillow Cython contextlib2
# Install pytorch
RUN pip3 install torch torchvision

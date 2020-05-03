FROM tensorflow/tensorflow:2.1.0-gpu-py3-jupyter

MAINTAINER genmai

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
    python-tk\
    cpio \
    git \
    sudo && \
    apt clean

# pipインストール 
RUN pip3 install opencv-python opencv-contrib-python imageio scikit-image lxml pillow Cython contextlib2

# reserch modelへPathを通す
ENV PYTHONPATH=$PYTHONPATH:/tf/work/tf2/models/research:/tf/work/tf2/models/research/slim:

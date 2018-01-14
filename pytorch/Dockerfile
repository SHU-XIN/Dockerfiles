FROM nvidia/cuda:8.0-cudnn7-devel-ubuntu16.04

# Install git, wget and other dependencies
RUN apt-get update && apt-get install -y python-pip
RUN apt-get install -y python3-pip
RUN pip install --upgrade pip
RUN pip3 install --upgrade pip
RUN apt-get update && apt-get install -y \
  git \
  python-dev \
  python-numpy \
  python-pip \
  python-setuptools \
  wget
RUN pip3 install \
  ipython \
  jupyter \
  numpy \
  scipy \
  matplotlib
RUN pip3 install -U scikit-image

RUN pip3 install http://download.pytorch.org/whl/cu80/torch-0.3.0.post4-cp35-cp35m-linux_x86_64.whl \
  torchvision \
  git+https://github.com/pytorch/tnt.git@master

EXPOSE 8888
WORKDIR /root/workspace

FROM nvidia/cuda:9.0-cudnn7-devel-ubuntu16.04

# Install git, wget and other dependencies
RUN apt-get update && apt-get install -y python-pip
RUN apt-get install -y python3-pip
RUN pip3 install --upgrade pip3
RUN pip install --upgrade pip
RUN apt-get update && apt-get install -y \
  git \
  python-dev \
  python-numpy \
  python-pip \
  python-setuptools \
  wget
RUN pip install \
  ipython \
  jupyter \
  numpy \
  scipy \
  matplotlib
RUN pip install -U scikit-image

RUN pip3 install http://download.pytorch.org/whl/cu90/torch-0.3.0.post4-cp35-cp35m-linux_x86_64.whl \
  pip3 install torchvision
  pip3 install git+https://github.com/pytorch/tnt.git@master

EXPOSE 8888
WORKDIR /root/workspace

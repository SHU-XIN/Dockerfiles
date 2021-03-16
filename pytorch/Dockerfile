FROM nvidia/cuda:10.1-devel-ubuntu14.04

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
  opencv-python \
  scikit-learn \
  matplotlib
RUN pip3 install -U scikit-image

RUN pip3 install torch==1.7.1+cu101 torchvision==0.8.2+cu101 torchaudio==0.7.2 -f https://download.pytorch.org/whl/torch_stable.html

EXPOSE 8888
WORKDIR /root/workspace

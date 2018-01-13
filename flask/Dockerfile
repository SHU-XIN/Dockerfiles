FROM ubuntu:14.04

# Install git, wget and other dependencies
RUN apt-get update && apt-get install -y python-pip
RUN pip install --upgrade pip

RUN apt-get update && apt-get install -y \
  git \
  python-dev \
  python-numpy \
  python-pip \
  python-setuptools \
  wget \
  mysql-server \
  mysql-client \
  libmysqlclient-dev \
  nginx

RUN pip install \
  ipython \
  jupyter \
  numpy \
  scipy \
  matplotlib \
  mysql-python \
  flask-sqlalchemy \
  flask-login \
  flask-bootstrap \
  flask_restful \
  uwsgi
  

RUN pip install -U scikit-image


EXPOSE 8888
WORKDIR /root/workspace

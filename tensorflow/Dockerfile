#VERSION       1.0
FROM shuxin/cuda
MAINTAINER <shuxin>  

#install Java
# disable interactive functions 
ENV DEBIAN_FRONTEND noninteractive 
# set default java environment variable 
ENV JAVA_HOME /usr/lib/jvm/java-8-openjdk-amd64 
RUN apt-get install -y software-properties-common && \ 
add-apt-repository ppa:openjdk-r/ppa -y && \ 
apt-get update && \ 
apt-get install -y --no-install-recommends openjdk-8-jre && \ 
rm -rf /var/lib/apt/lists/*


RUN apt-get update && apt-get install -y python-pip
RUN pip install --upgrade pip
# install ipython 
# install jupyter 
RUN pip install ipython jupyter
# plot figures 
RUN pip install matplotlib
# dependecy package of mx.viz.plot_network 
RUN pip install graphviz
# following command ensures the visualization of mx.viz.plot_network in ipython notebook 
RUN apt-get install -y graphviz
RUN apt-get install python-opencv
#image processing 
RUN pip install scipy
#RUN pip install -U scikit-image
RUN pip install Flask

#install tensorflow
RUN pip install --upgrade six
TF_BINARY_URL = https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow-0.9.0-cp27-none-linux_x86_64.whl
RUN pip install --upgrade $TF_BINARY_URL

# expose 8888 as jupyter's default 
EXPOSE 8888 
EXPOSE 8787 
EXPOSE 7777 
EXPOSE 9797 
# Set a seperated workspace as working directory 
WORKDIR /root/workspace
# Optionally expose the workspace to the host 
VOLUME ["/root/workspace"]
# Add Tini.  Tini operates as a process subreaper for jupyter. This prevents kernel crashes. 
ENV TINI_VERSION v0.8.4 
ADD https://github.com/krallin/tini/releases/download/${TINI_VERSION}/tini /usr/bin/tini 
RUN chmod +x /usr/bin/tini
ENTRYPOINT ["/usr/bin/tini", "--"]
# Run notebook for ipython defaultly 
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8888","--no-browser"]

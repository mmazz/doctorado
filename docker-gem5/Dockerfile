FROM ubuntu:16.04
RUN apt-get update

RUN apt -y update && apt -y upgrade && \
    apt -y install build-essential git m4 scons zlib1g zlib1g-dev \
    libprotobuf-dev protobuf-compiler libprotoc-dev libgoogle-perftools-dev \
    python3-dev python3 doxygen libboost-all-dev \
    libhdf5-serial-dev python3-pydot libpng-dev libelf-dev pkg-config \
    python3-pip python3-venv
RUN pip3 install black mypy pre-commit
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 10
RUN update-alternatives --install /usr/bin/python python /usr/bin/python2 1
RUN useradd -m mmazz
RUN echo "mmazz:mmazz" | chpasswd
RUN usermod -aG sudo mmazz
RUN apt -y install vim
RUN apt -y install gcc-4.8
RUN apt -y install g++-4.8
RUN apt update
RUN apt install --reinstall build-essential
#RUN useradd -ms /bin/bash -g root -aG sudo -u 1000 mmazz
#RUN echo 'mmazz:mmazz' | chpasswd
USER mmazz

FROM ubuntu:16.04
#RUN apt -y update && apt -y upgrade && \
#    apt -y install build-essential git m4 scons zlib1g zlib1g-dev \
#    libprotobuf-dev protobuf-compiler libprotoc-dev libgoogle-perftools-dev \
#    python3-dev python3 doxygen libboost-all-dev \
#    libhdf5-serial-dev python3-pydot libpng-dev libelf-dev pkg-config \
#    python3-pip python3-venv
#RUN pip3 install black mypy pre-commit
#RUN update-alternatives --install /usr/bin/python python /usr/bin/python3 10
#RUN update-alternatives --install /usr/bin/python python /usr/bin/python2 1
RUN apt update -y && apt upgrade -y
RUN apt -y install sudo vim
RUN useradd -m mmazz
RUN echo "root:espada" | chpasswd
RUN echo "mmazz:espada" | chpasswd
RUN usermod -aG sudo mmazz
RUN echo "%mmazz ALL=(ALL) ALL" >> /etc/sudoers
WORKDIR /home/mmazz
RUN apt -y install build-essential git m4 zlib1g zlib1g-dev libprotobuf-dev protobuf-compiler libprotoc-dev libgoogle-perftools-dev

RUN apt -y install curl wget gcc-4.8 g++-4.8
RUN apt -y install software-properties-common
RUN apt-key adv --refresh-keys --keyserver keyserver.ubuntu.com
RUN apt -y update
RUN add-apt-repository -y ppa:jblgf0/python
RUN add-apt-repository ppa:ubuntu-toolchain-r/test


RUN apt -y update

RUN apt -y install python3.9 python3.9-dev g++-9 python3.9-distutils
RUN curl https://bootstrap.pypa.io/get-pip.py -o get-pip.py | python3.9 - --user
RUN update-alternatives --install /usr/bin/python python /usr/bin/python3.9 2
RUN update-alternatives --config python

RUN apt -y install --reinstall build-essential

RUN python get-pip.py
RUN python -m pip install black mypy pre-commit
RUN python -m pip install python-config
RUN python -m pip install scons==3.1.2
RUN apt -y install gcc-9 g++-9
RUN update-alternatives --install /usr/bin/gcc gcc /usr/bin/gcc-9 60 \
                         --slave /usr/bin/g++ g++ /usr/bin/g++-9
RUN update-alternatives --config gcc
RUN echo PATH=$PATH:~/.local/bin
RUN update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.9 1
RUN update-alternatives --config python
RUN ln -sf /usr/bin/python3.9-config /usr/bin/python-config
RUN apt -y update
RUN apt -y upgrade




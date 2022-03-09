FROM ubuntu:20.04

RUN apt-get update \
    && apt-get upgrade -y \
    && apt install -y lsb-release wget software-properties-common flex bison 
RUN bash -c "$(wget -O - https://apt.llvm.org/llvm.sh)" 
RUN apt-get install g++

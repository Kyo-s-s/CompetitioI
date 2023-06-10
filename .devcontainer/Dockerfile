FROM archlinux:base-devel

RUN pacman -Syyu --noconfirm \
    gcc \
    gdb \
    git \
    python-pip \
    boost

RUN pip3 install online-judge-tools

RUN pip3 install online-judge-verify-helper

WORKDIR /workspace

FROM archlinux:base-devel

RUN pacman -Syyu --noconfirm \
    gcc \
    gdb \
    git \
    python-pip

RUN pip3 install online-judge-verify-helper

WORKDIR /workspace

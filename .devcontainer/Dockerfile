FROM archlinux:base-devel

RUN pacman -Syyu --noconfirm \
    gcc \
    gdb \
    git \
    python-pip \
    boost \
    ruby-bundler \
    sudo

RUN python -m venv /workspace/venv

ENV PATH="/workspace/venv/bin:$PATH"

RUN pip install online-judge-tools
RUN pip install online-judge-verify-helper

ARG UID=1000
ARG GID=1000
RUN groupadd -g $GID dev \
    && useradd -m -u ${UID} -g ${GID} dev \
    && echo "dev ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER dev

WORKDIR /workspace
FROM archlinux:base-devel

RUN pacman -Syyu --noconfirm \
    gcc \
    gdb \
    git \
    boost \
    python \
    python-pipx \
    sudo


RUN pipx install online-judge-tools
RUN pipx install online-judge-verify-helper

RUN echo 'export PATH="/home/dev/.local/bin:$PATH"' >> ~/.bashrc
RUN source ~/.bashrc

ARG UID=1000
ARG GID=1000
RUN groupadd -g $GID dev \
    && useradd -m -u ${UID} -g ${GID} dev \
    && echo "dev ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

USER dev

WORKDIR /workspace
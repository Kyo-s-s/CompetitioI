FROM archlinux:base-devel

ARG UID=1000
ARG GID=1000
RUN groupadd -g $GID dev \
    && useradd -m -u ${UID} -g ${GID} dev \
    && echo "dev ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers

RUN pacman -Syyu --noconfirm \
    gcc \
    gdb \
    git \
    boost \
    python \
    python-pipx \
    sudo \
    vi

USER dev

RUN pipx install online-judge-tools
RUN pipx install online-judge-verify-helper

RUN echo 'export PATH="/home/dev/.local/bin:$PATH"' >> ~/.bashrc

RUN echo -e "\n\
gpp() {\n\
    g++ -std=c++20 \$1.cpp\n\
}\n\
gppt() {\n\
    gpp \$1\n\
    oj t\n\
}\n\
" >> ~/.bashrc

RUN source ~/.bashrc

WORKDIR /home/dev/work
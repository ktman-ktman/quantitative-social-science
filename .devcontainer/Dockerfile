ARG VARIANT="latest"

FROM julia:${VARIANT}

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    fish \
    git \
    htop \
    python3.9 \
    python3.9-dev \
    python3-pip \
    python3.9-venv \
    tmux \
    wget \
    && apt-get -y clean \
    && rm -rf /var/lib/apt/lists/*

RUN pip3 install -U pip \
    && pip3 install matplotlib

# user
ARG USERNAME="vscode"
ARG USER_UID="1000"
ARG USER_GID=${USER_UID}

RUN groupadd --gid ${USER_GID} ${USERNAME} \
    && useradd --uid ${USER_UID} --gid ${USER_GID} -m ${USERNAME}

CMD ["/bin/bash"]
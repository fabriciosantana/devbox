FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

ENV DEBIAN_FRONTEND=noninteractive

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Complementos essenciais para aula e GitHub Codespaces.
RUN apt-get update \
    && apt-get install -y --no-install-recommends \
        ca-certificates \
        curl \
        git-lfs \
        gnupg \
        unzip \
        zip \
    && install -m 0755 -d /etc/apt/keyrings \
    && curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg \
        -o /etc/apt/keyrings/githubcli-archive-keyring.gpg \
    && chmod go+r /etc/apt/keyrings/githubcli-archive-keyring.gpg \
    && echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" \
        > /etc/apt/sources.list.d/github-cli.list \
    && apt-get update \
    && apt-get install -y --no-install-recommends gh \
    && git lfs install --system \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

USER vscode

ENV SDKMAN_DIR=/home/vscode/.sdkman
ENV SDKMAN_AUTO_ANSWER=true
ARG JAVA_VERSION
ARG MAVEN_VERSION

RUN curl -fsSL "https://get.sdkman.io?ci=true&rcupdate=false" | bash \
    && source "${SDKMAN_DIR}/bin/sdkman-init.sh" \
    && sdk install java "${JAVA_VERSION}" \
    && sdk install maven "${MAVEN_VERSION}" \
    && sdk flush archives \
    && sdk flush temp \
    && echo "source ${SDKMAN_DIR}/bin/sdkman-init.sh" >> /home/vscode/.bashrc

ENV JAVA_HOME=${SDKMAN_DIR}/candidates/java/current
ENV MAVEN_HOME=${SDKMAN_DIR}/candidates/maven/current
ENV PATH=${JAVA_HOME}/bin:${MAVEN_HOME}/bin:${PATH}

CMD ["bash"]

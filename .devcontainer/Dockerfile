# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.217.4/containers/debian/.devcontainer/base.Dockerfile

# [Choice] Debian version (use bullseye on local arm64/Apple Silicon): bullseye, buster
ARG VARIANT="buster"
FROM mcr.microsoft.com/vscode/devcontainers/base:0-${VARIANT}

# ** [Optional] Uncomment this section to install additional packages. **
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    libc6-dev gcc gdb make

# Install Java
ENV JAVA_HOME /usr/local/openjdk-8
ENV PATH="$JAVA_HOME/bin:$PATH"
COPY --from=openjdk:8-buster $JAVA_HOME $JAVA_HOME

# Install Dart
ENV DART_SDK /usr/lib/dart
ENV PATH="$PATH:/usr/lib/dart/bin"
COPY --from=dart:stable $DART_SDK $DART_SDK


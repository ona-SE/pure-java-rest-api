FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    curl \
    wget \
    git \
    && apt-get clean -y && rm -rf /var/lib/apt/lists/*

ENV MAVEN_VERSION=3.9.9
ENV MAVEN_HOME=/opt/maven
ENV PATH=${MAVEN_HOME}/bin:${PATH}

RUN wget https://archive.apache.org/dist/maven/maven-3/${MAVEN_VERSION}/binaries/apache-maven-${MAVEN_VERSION}-bin.tar.gz -O /tmp/maven.tar.gz \
    && mkdir -p ${MAVEN_HOME} \
    && tar -xzf /tmp/maven.tar.gz -C ${MAVEN_HOME} --strip-components=1 \
    && rm /tmp/maven.tar.gz

FROM centos:8
LABEL maintainer="yago.riveiro@gmail.com"

ARG VERSION=1.12
ARG URL=https://github.com/tianon/gosu/releases/download/${VERSION}/gosu-amd64
ARG GOSU_SHA256="0f25a21cf64e58078057adc78f38705163c1d564a959ff30a891c31917011a54"

SHELL ["/bin/bash", "-eo", "pipefail", "-c"]
RUN yum install -y \
    curl-7.61.1-11.el8.x86_64 \
    bash-4.4.19-10.el8.x86_64 && \
    curl -L --fail --silent --show-error ${URL} > /usr/local/bin/gosu && \
    echo "${GOSU_SHA256}  /usr/local/bin/gosu" | sha256sum -c --quiet && \
    chmod +x /usr/local/bin/gosu && \
    yum clean all

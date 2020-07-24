FROM perlur/centos-base

ARG BUILD_DATE
ENV SERVICE_NAME "haskell-ghcup"

LABEL org.label-schema.schema-version="1.0" \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="PERLUR CentOS Haskell Platform Builder Image" \
      org.label-schema.license="AGPL-3.0-or-later" \
      org.label-schema.vendor="PERLUR Group"
LABEL org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.authors="Mark Stopka <mark.stopka@perlur.cloud>" \
      org.opencontainers.image.vendor="PERLUR Group"

LABEL maintainer="Mark Stopka <mark.stopka@perlur.cloud>"

RUN yum update -y && \
    yum install -y gcc gcc-c++ git-core gmp gmp-devel make ncurses ncurses-compat-libs xz perl
RUN curl -L -o /usr/local/bin/ghcup --proto '=https' --tlsv1.2 -sSf https://downloads.haskell.org/~ghcup/x86_64-linux-ghcup
RUN chmod +x /usr/local/bin/ghcup
RUN ghcup install-cabal
RUN dnf clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/cache/dnf
ENV PATH $PATH:/root/.ghcup/bin

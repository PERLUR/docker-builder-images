FROM perlur/centos-base

MAINTAINER "Mark Stopka <mark.stopka@perlur.cloud>"

ENV SERVICE_NAME "haskell-ghcup"

RUN yum update -y && \
    yum install -y gcc gcc-c++ git-core gmp gmp-devel make ncurses ncurses-compat-libs xz perl
RUN curl -L -o /usr/local/bin/ghcup --proto '=https' --tlsv1.2 -sSf https://downloads.haskell.org/~ghcup/x86_64-linux-ghcup
RUN chmod +x /usr/local/bin/ghcup
RUN ghcup install-cabal
RUN dnf clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/cache/dnf
ENV PATH $PATH:/root/.ghcup/bin

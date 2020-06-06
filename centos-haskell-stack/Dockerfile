FROM perlur/centos-base

MAINTAINER "Mark Stopka <mark.stopka@perlur.cloud>"

ENV SERVICE_NAME "haskell-stack"

RUN yum update -y
RUN curl -L --proto '=https' --tlsv1.2 -sSf https://get.haskellstack.org/ | sh -s --
RUN yum clean all && \
    dnf clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/cache/dnf
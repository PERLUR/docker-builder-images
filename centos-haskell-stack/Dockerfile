FROM perlur/centos-base

MAINTAINER "Mark Stopka <mark.stopka@perlur.cloud>"

ENV SERVICE_NAME "haskell-stack"

RUN yum update -y
RUN yum clean all && \
    dnf clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/cache/dnf
RUN curl --proto '=https' --tlsv1.2 -sSf https://get.haskellstack.org/ | sh -s --

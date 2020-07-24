FROM perlur/centos-base

ARG BUILD_DATE
ENV SERVICE_NAME "ocaml-opam"

LABEL org.label-schema.schema-version="1.0" \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="PERLUR CentOS Haskell Stack Builder Image" \
      org.label-schema.license="AGPL-3.0-or-later" \
      org.label-schema.vendor="PERLUR Group"
LABEL org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.authors="Mark Stopka <mark.stopka@perlur.cloud>" \
      org.opencontainers.image.vendor="PERLUR Group"

LABEL maintainer="Mark Stopka <mark.stopka@perlur.cloud>"

RUN yum update -y && \
    yum install -y bubblewrap bzip2 gcc git-core m4 make openssl patch unzip
RUN curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/ocaml/opam/master/shell/install.sh | sh -s
RUN yum clean all && \
    dnf clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/cache/dnf
RUN opam init --disable-sandboxing

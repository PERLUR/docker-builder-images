FROM perlur/centos-base

MAINTAINER "Mark Stopka <mark.stopka@perlur.cloud>"

ENV SERVICE_NAME "ocaml-opam"

RUN yum update -y && \
    yum install -y bubblewrap bzip2 gcc git-core m4 make openssl patch unzip
RUN curl --proto '=https' --tlsv1.2 -sSf https://raw.githubusercontent.com/ocaml/opam/master/shell/install.sh | sh -s
RUN yum clean all && \
    dnf clean all && \
    rm -rf /var/cache/yum && \
    rm -rf /var/cache/dnf
RUN opam init --disable-sandboxing

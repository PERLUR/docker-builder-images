FROM ghcr.io/perlur/opensuse-leap-base:latest

ARG BUILD_DATE
ENV SERVICE_NAME "haskell-ghcup"

LABEL org.label-schema.schema-version="1.0" \
      org.label-schema.build-date=$BUILD_DATE \
      org.label-schema.name="PERLUR openSUSE Leap Haskell Platform Builder Image" \
      org.label-schema.license="AGPL-3.0-or-later" \
      org.label-schema.vendor="PERLUR Group"
LABEL org.opencontainers.image.created=$BUILD_DATE \
      org.opencontainers.image.authors="Mark Stopka <mark.stopka@perlur.cloud>" \
      org.opencontainers.image.vendor="PERLUR Group"

LABEL maintainer="Mark Stopka <mark.stopka@perlur.cloud>"

RUN zypper refresh 
RUN zypper update -y
RUN zypper install -y curl git-core python3 gcc make  
RUN rm -rf /var/cache/zypp
RUN curl -L -o /usr/local/bin/ghcup --proto '=https' --tlsv1.2 -sSf https://downloads.haskell.org/~ghcup/x86_64-linux-ghcup
RUN chmod +x /usr/local/bin/ghcup
RUN ghcup install-cabal
ENV PATH $PATH:/root/.ghcup/bin

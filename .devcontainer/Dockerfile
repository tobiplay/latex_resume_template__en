# Pull the base image:
FROM mcr.microsoft.com/devcontainers/base:jammy

# Install XeTeX and the (required) packages:
RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
    && apt-get -y install --no-install-recommends \
    g++ \
    make \
    wget \
    texlive-full \
    biber \
    && apt-get clean && rm -rf /var/lib/apt/lists/*

RUN apt-get update -y && \
    apt-get install -y --no-install-recommends cpanminus gcc libc6-dev && \
    cpanm -n -q Log::Log4perl && \
    cpanm -n -q XString && \
    cpanm -n -q Log::Dispatch::File && \
    cpanm -n -q YAML::Tiny && \
    cpanm -n -q File::HomeDir && \
    cpanm -n -q Unicode::GCString && \
    apt-get remove -y cpanminus make gcc libc6-dev && \
    apt-get clean autoclean && \
    apt-get autoremove -y && \
    rm -rf /var/lib/{apt,dpkg,cache,log}/

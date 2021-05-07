FROM debian:latest

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update \
 && apt-get install -y --no-install-recommends \
    git \
    curl \
    ca-certificates \
    build-essential \
    libssl-dev \
    pkg-config \
 && apt-get -y clean \
 && rm -rf /var/lib/apt/lists/*

RUN curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh -s -- -y
RUN /root/.cargo/bin/rustup component add \
    rls \
    rust-analysis \
    rust-src
RUN /root/.cargo/bin/cargo install \
    cargo-edit
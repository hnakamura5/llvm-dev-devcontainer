FROM mcr.microsoft.com/devcontainers/base:ubuntu-24.04

# https://apt.llvm.org/
RUN wget https://apt.llvm.org/llvm.sh \
    && chmod +x llvm.sh

RUN apt-get update \
    && apt-get install -y --no-install-recommends \
    curl \
    lsb-release \
    wget \
    gnupg \
    software-properties-common \
    # Install LLVM 22 basic packages and setup gpg keys
    && ./llvm.sh 22 all \
    # Install LLVM 22 additional development packages
    && apt-get install -y --no-install-recommends \
    # compiler-rt
    libclang-rt-22-dev \
    # mlir
    libmlir-22-dev \
    mlir-22-tools \
    && rm -rf /var/lib/apt/lists/* \
    && apt clean


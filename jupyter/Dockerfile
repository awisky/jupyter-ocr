FROM jupyter/minimal-notebook:latest

USER root

# Update aptitude with new repo
RUN apt-get update \
    && apt-get install -y git

COPY ./requirements.txt ./

# Configure apt and install packages
RUN apt-get update -y && \
    apt-get install -y \
    libglib2.0-0 \
    libsm6 \
    libxext6 \
    libxrender-dev \
    libgl1-mesa-dev \
    poppler-utils \
    wget \
    git \
    # cleanup
    && apt-get autoremove -y \
    && apt-get clean -y \
    && rm -rf /var/lib/apt/li

# Install Python3 and all the requirements.txt
RUN apt-get update && apt-get install -y --no-install-recommends \
        apt-utils \
        python3-dev \
        python3-wheel \
    && pip3 install --upgrade pip \
    && pip3 install -r requirements.txt

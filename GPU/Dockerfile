# we are re building the base container from the mltooling/ml-workspace-minimal:0.9.1 Dockerfile on GitHub
# to ensure that we know exactly what is in it 

FROM mltooling/ml-workspace-gpu:0.9.1

USER root

# Install a few dependencies for iCommands, text editing, and monitoring instances
RUN apt-get update && apt-get install -y \
    apt-transport-https \
    gcc \
    gnupg \
    htop \
    less \
    libfuse2 \
    libpq-dev \
    libssl1.0 \
    lsb \
    nano \
    nodejs \
    python-requests \
    software-properties-common \
    vim

# Install iCommands
RUN wget -qO - https://packages.irods.org/irods-signing-key.asc | apt-key add - \
    && echo "deb [arch=amd64] https://packages.irods.org/apt/ bionic main" | tee /etc/apt/sources.list.d/renci-irods.list \
    && apt-get update && apt-get install -y irods-runtime irods-icommands
   
COPY GPU/irods_environment.json /home/jovyan/.irods/irods_environment.json

# ENTRYPOINT is set in mltooling/ml-workspace-minimal:0.9.1 container

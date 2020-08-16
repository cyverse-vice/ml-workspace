# we are re building the base container from the mltooling/ml-workspace-minimal:0.9.1 Dockerfile on GitHub
# to ensure that we know exactly what is in it 

FROM cyversevice/ml-workspace-minimal:0.9.1

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
RUN wget https://files.renci.org/pub/irods/releases/4.1.10/ubuntu14/irods-icommands-4.1.10-ubuntu14-x86_64.deb && dpkg -i *.deb
   
COPY irods_environment.json /root/.irods/irods_environment.json

# ENTRYPOINT is set in mltooling/ml-workspace-minimal:0.9.1 container

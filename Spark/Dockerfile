# we are re building the base container from the mltooling/ml-workspace-minimal:0.9.1 Dockerfile on GitHub
# to ensure that we know exactly what is in it 

FROM cyversevice/ml-workspace-minimal:0.9.1

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
    
# Add the jovyan user to UID 1000
RUN groupadd jovyan && usermod -aG jovyan jovyan && usermod -d /home/jovyan -u 1000 jovyan
RUN chown -R jovyan:jovyan /home/jovyan
USER jovyan
WORKDIR /home/jovyan    

RUN mkdir -p /home/jovyan/.irods
COPY irods_environment.json /home/jovyan/.irods/irods_environment.json

# ENTRYPOINT is set in mltooling/ml-workspace-minimal:0.9.1 container

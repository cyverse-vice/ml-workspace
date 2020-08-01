[![Project Supported by CyVerse](https://img.shields.io/badge/Supported%20by-CyVerse-blue.svg)](https://learning.cyverse.org/projects/vice/en/latest/) [![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active) [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.3903534.svg)](https://doi.org/10.5281/zenodo.3903534) [![license](https://img.shields.io/badge/license-GPLv3-blue.svg)](https://opensource.org/licenses/GPL-3.0)

# ml-workspace

This `ml-workspace` base image is built upon [Ml-tooling's project](https://hub.docker.com/r/mltooling/ml-workspace) for [CyVerse](https://cyverse-visual-interactive-computing-environment.readthedocs-hosted.com/en/latest/index.html). Ml-tooling's base Jupyter image requires additional configuration files for it to fully exploit CyVerse iRODS data store.

[![CircleCI](https://circleci.com/gh/cyverse-vice/ml-workspace.svg?style=svg)](https://circleci.com/gh/cyverse-vice/ml-workspace) [![DockerHub](https://img.shields.io/badge/DockerHub-brightgreen.svg?style=popout&logo=Docker)](https://hub.docker.com/r/cyversevice/ml-workspace)

quick launch | tag | size | metrics | build | 
------------ | --- | ---- | ------- | ------|
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | [![TAG](https://images.microbadger.com/badges/version/cyversevice/ml-workspace:minimal.svg)](https://microbadger.com/images/cyversevice/ml-tooling:minimal) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/ml-tooling:minimal.svg)](https://microbadger.com/images/cyversevice/ml-tooling:minimal) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/ml-tooling?color=blue&label=pulls&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/ml-tooling?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling)
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | [![TAG](https://images.microbadger.com/badges/version/cyversevice/ml-workspace:light.svg)](https://microbadger.com/images/cyversevice/ml-tooling:light) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/ml-tooling:light.svg)](https://microbadger.com/images/cyversevice/ml-tooling:light) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/ml-tooling?color=blue&label=pulls&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/ml-tooling?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling)
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | [![TAG](https://images.microbadger.com/badges/version/cyversevice/ml-workspace:gpu.svg)](https://microbadger.com/images/cyversevice/ml-tooling:gpu) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/ml-tooling:gpu.svg)](https://microbadger.com/images/cyversevice/ml-tooling:gpu) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/ml-tooling?color=blue&label=pulls&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/ml-tooling?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling)
<a href="" target="_blank"><img src="https://de.cyverse.org/Powered-By-CyVerse-blue.svg"></a> | [![TAG](https://images.microbadger.com/badges/version/cyversevice/ml-workspace:r.svg)](https://microbadger.com/images/cyversevice/ml-tooling:r) | [![SIZE](https://images.microbadger.com/badges/image/cyversevice/ml-tooling:r.svg)](https://microbadger.com/images/cyversevice/ml-tooling:r) | [![Docker Pulls](https://img.shields.io/docker/pulls/cyversevice/ml-tooling?color=blue&label=pulls&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling) | [![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/cyversevice/ml-tooling?color=blue&logo=docker&logoColor=white)](https://hub.docker.com/r/cyversevice/ml-tooling)

# Instructions

## Run Docker container locally or on a Virtual Machine

To run ml-tooling, you must first `pull` from DockerHub, or activate a [CyVerse Account](https://user.cyverse.org/services/mine) and launch in the Discovery Environment VICE.

The container for running ml-tooling is hosted on DockerHub and can be started locally:


```
docker pull cyversevice/ml-workspace:latest
```

```
docker run -it --rm -d cyversevice/ml-workspace:latest
```

Run with NVIDIA GPU

```
docker run --gpus all -it --rm -d -e NVIDIA_DRIVER_CAPABILITIES=all cyversevice/ml-workspace:latest
```

## Run Docker container in CyVerse VICE

Unless you plan on making changes to this container, you should just use the existing launch button above.

You can build a new Docker container with additional dependencies from this Docker Hub image by using the `FROM cyversevice/ml-workspace:latest` at the beginning of your own Dockerfile.

###### Developer notes

To test the container locally:

```
docker run -it --rm -v /$HOME:/app --workdir /app -p 8888:8888 -e REDIRECT_URL=http://localhost:8888 cyversevice/ml-workspace:latest
```

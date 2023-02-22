# Hadoop pseudo distributed mode dockerized
Flexible Hadoop Docker image to aid local development. This repo extends the original repo to run hadoop on apple silicon with latest versionset.

## Quick start
[Download](https://www.docker.com) docker if you haven't installed it yet.

Start the container using:
```
docker-compose up -d
```
The `docker-compose.yml` defines an external network `xapp` where the Hadoop cluster is placed.

## Usage
Attach and interact with the container by running `docker-compose exec hadoop bash` or `docker run -it <container id>`.

The `/home` directory of the container is binded to the parent directory of this repo. It can used as a shared folder between the host and container to access and run `.jars`. Check `volumes` in `docker-compose.yml` to update the binded folders if required.

## Web interfaces
* Namenode <http://localhost:9870>  
* Secondary namenode <http://localhost:9868>  
* Datanode <http://localhost:9864>  
* Resource manager <http://localhost:8088>  
* Node manager <http://localhost:8042>  

## Configuration
The image only uses default configuration. Customization can be done by modifying the files inside the Hadoop configurations folder.  
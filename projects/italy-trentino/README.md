
# Trentino geocoder
This project is configured to download/prepare/build a complete Pelias installation for Trentino Alto Adige in Italy

# Setup
Please refer to the instructions at https://github.com/pelias/docker in order to install and configure your docker environment.

The file *.env* contains custom ENV variable passed to docker compose to specify
data working directory and docker connection parameters:
```
COMPOSE_PROJECT_NAME=pelias
DOCKER_USER=1000
DOCKER_HOST=unix:///var/run/docker.sock
DATA_DIR=/data
PELIAS_CONFIG=/var/www/pelias/docker/projects/italy-trentino/pelias.json
```
*PELIAS_CONFIG* is absolute path di locate pelias config file

# Run a Build
To run a complete build configure and execute the script *build.sh*
or the following commands separately:

```bash
pelias compose pull
pelias elastic start
pelias elastic wait
pelias elastic create
pelias download all
pelias prepare all
pelias import all
pelias compose up
```

## API CONFIGI

defaults values:
https://github.com/pelias/config/blob/master/config/defaults.json
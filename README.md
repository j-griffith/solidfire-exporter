# NetApp Solidfire Exporter

Prometheus NetApp solidfire-exporter queries the Solidfire API and exports the results as Prometheus metrics

![Go](https://github.com/mjavier2k/solidfire-exporter/workflows/Go/badge.svg?event=push)

Implementation is based on [Solidfire 11.3 API](https://library.netapp.com/ecm/ecm_download_file/ECMLP2856155)

## Goals
- Volume QoS stats
- Volume stats
- Node stats
- Fault stats
- Cluster stats

## Defaults for environment variables

```
SOLIDFIRE_USER=monitoring_user
SOLIDFIRE_PASS=monitoring_password
SOLIDFIRE_RPC_ENDPOINT=https://192.168.1.1/json-rpc/11.3
INSECURE_SKIP_VERIFY=false
PORT=9987
```

## Volume QoS

SOLIDFIRE_USER must have administrator access to be able to gather volume qos data


## Using Docker

Create an file with the environment variables set and pass it to docker run. 

```
docker run --env-file=.env_file  --rm -p 8080:8080 mjavier/solidfire-exporter:latest
```

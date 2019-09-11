# ZADARA real-time monitoring using python/django-prometheus-influxdb-cn-architecture, aka ZYMON
Zymon, a Hebrew name for "listening". The recommended pronounciation is "Zay-Mahn"

## Architecture: System Context

<p align="center">
  <img width="600" height="400" src="architecture/images/zadara%20monitor%20system%20context.png">
</p>

## Architecture: Framework Components

<p align="center">
  <img width="600" height="300" src="architecture/images/django%20framework%20to%20monitor%20zadara.png">
</p>

## Dependencies
You'll need [Docker](https://docs.docker.com/install/) installed and a Kubernetes cluster to deploy Prometheus to ([Minikube](https://kubernetes.io/docs/setup/learning-environment/minikube/) should work just fine, or [CodeReady](https://code-ready.github.io/crc/)). As Dev, you'll also need the kubectl client and helm in order to control and manage k8 deployments. You'll also need to install the [Tiller](https://helm.sh/docs/install/) server into the cluster and have the client available locally.

## Local Development

```
docker-compose up -d
```

### Install the Web App in a K8 cluster

```
# in real life, we wouldnt VC the .htpasswd, but this is easy. Have one created using vim.
kubectl create secret generic prometheus-basic-auth --from-file=.htpasswd=prometheus/.htpasswd
make
```

### Install InfluxDB App

```
# xxx blah
```

### Install the Prometheus helm chart

```
helm install --name zymon -f helm/prometheus/values.yaml
#helm upgrade --install prometheus stable/prometheus -f helm/prometheus/values.yaml
```

### Testing

```
xxx blah
```




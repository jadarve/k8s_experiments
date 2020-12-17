# K8S Experiments

Exploring Kubernetes

## Setup

* Start a minikube cluster

```
minikube start
```

* Start Skaffold in dev mode

```
skaffold dev
```

* Expose `hello` deployment as a service

**FIXME:** Can this be described in a `.yaml`?
```
kubectl expose deployment hello --type=NodePort --name=hello-service
```

* Get the service URL

```
minikube service hello-service --url
```

* Test accessing the service

```
http://192.168.99.100:32695
```
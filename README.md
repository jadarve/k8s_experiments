# K8S Experiments

Exploring Kubernetes

## Setup

* Start a minikube cluster and enable the ingress addon

```
minikube start
minikube addons enable ingress
```

* Start Skaffold in dev mode

```
skaffold dev
```

### Get the service URL directly

```
minikube service hello-service --url

curl <url from previous command>
```

### Get the services URLs through the ingress

```
kubectl get ingress
```

Output should look like this:

```
NAME            CLASS    HOSTS         ADDRESS          PORTS   AGE
local-ingress   <none>   hello.local   192.168.99.100   80      3m20s
```

Insert the service URL into your `/etc/hosts` file

```
# Local minikube ingress hosts
192.168.99.100 hello.local
```

Test the service

```
curl http://hello.local/moni
```
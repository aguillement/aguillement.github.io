+++
date = '2024-10-23T11:15:08+02:00'
draft = false
title = 'Service Mesh'
+++

## Service Mesh, kesako?

Dans le monde des architecture micro-services, le réseau est le point central permettant la bonne communication entre les différents composants.
Service Mesh (maille/filet de service en français?) permet de gérer le traffic réseau entre les services

Cela permet 
 - la découverte de nouveaux services et de communiquer avec. Router le traffic intelligement des APIs entre les différents endpoints.
 - meilleure sécuritée, afin d'autoriser ou d'interdire certains flux
 - observabilité des services distribués.
 - chiffrement de la communication pod-to-pod (East-West Traffic)

### Les services mesh les plus répandus

Istio :
Consul Connect
Linkerd

| | Istio | Consul Connect | Linkerd |
|---|---|---|---|
| Architecture |Kubernetes + VMs |Kubernetes + VMs|Kubernetes|
| Un agent par node |non |oui|non|
| mTLS |oui |oui|oui|
| gestion de certificat |oui |oui|oui|
| HTTP |oui |oui|oui|
| TCP |oui |oui|oui|
| gRPC |oui |oui|oui|
| Rate limit |oui |oui|non|

## Test istio

https://istio.io/

J'utilise kind en local pour reproduire un cluster avec docker.

```
kind create cluster --name istio
```

```
kubectl config use-context kind-istio
```

Une fois terminé, suppression du cluster local :
```
kind delete cluster --name istio-
```

# k8s-operator

Custom mem-cached operator for Kubernetes.

An Operator is a method of packaging, deploying and managing a Kubernetes application. 

A Kubernetes application is an application that is both deployed on Kubernetes and managed using the Kubernetes APIs and kubectl tooling.

Pre-requisites:

* GoLang

* [Operator SDK](https://github.com/operator-framework/operator-sdk)

# Development

#### Docker

1) Docker build

```bash
operator-sdk build m-wrona/k8s-memcached-operator
```

2) Docker push

```bash
docker push m-wrona/k8s-memcached-operator
```

# Doc

* [Operator overview](https://coreos.com/operators/)

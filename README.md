# k8s-operator

Custom mem-cached operator for Kubernetes.

An Operator is a method of packaging, deploying and managing a Kubernetes application. 

A Kubernetes application is an application that is both deployed on Kubernetes and managed using the Kubernetes APIs and kubectl tooling.

Pre-requisites:

* GoLang

* [Operator SDK](https://github.com/operator-framework/operator-sdk)

# Development

#### Local development

1) Set the name of the operator in an environment variable

```bash
export OPERATOR_NAME=memcached-operator
```

2) Run locally

```bash
operator-sdk up local --namespace=default
```

#### Build

1) Regenerate K8s related code

```bash
operator-sdk generate k8s
``` 

#### Docker

1) Docker build

```bash
operator-sdk build mwrona/k8s-memcached-operator:v0.0.1
```

2) Docker push

```bash
docker push mwrona/k8s-memcached-operator:v0.0.1
```

#### Kubernetes

1) Deploy K8s operator

```bash
kubectl create -f deploy/crds/cache_v1alpha1_memcached_crd.yaml
kubectl create -f deploy/service_account.yaml
kubectl create -f deploy/role.yaml
kubectl create -f deploy/role_binding.yaml
kubectl create -f deploy/operator.yaml
```

2) Create mem-cached

```bash
kubectl apply -f deploy/crds/cache_v1alpha1_memcached_cr.yaml
```

3) Check mem-cached status

```bash
kubectl get memcached/example-memcached -o yaml
```

# Doc

* [Operator overview](https://coreos.com/operators/)

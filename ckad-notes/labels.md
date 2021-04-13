## Where is the location of lables?

```
metadata:
  labels:
    env:uat
```

## How to check lables for the Pod

```
$ kubectl describe pod labeled-pod | grep -C 2 Labels
Labels:
   env=dev
   tier=backend    
```

## How to add, remove or update labels imperative way?

```
kubectl label pod labeled-pod region=eu
kubectl label pod labeled-pod region-
kubectl label pod labeled-pod region=eu
```

## Where is the pod selector in proxy objects like service, network policy and deployment?

```
spec:
  podSelector:
    matchLabels:
      tier: frontend
```

## What is the difference between annotation and lables?

```
Annotation is used for meta data cannot be queried or selected
kubectl annotate pod annotated-pod oncall='800-555-1212'pod/annotated-pod annotated
```

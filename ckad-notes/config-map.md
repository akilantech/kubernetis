## Where will config map show up in pod description?

```
environment
```

## How it is configured in the pod yaml?

```
spec:
 container:
 - env: 
   - name: APP_COLOR
     value: pink
```     

## What is shortcut command for config map?

```
kubectl get cm     
```

## What is imperative way to create config map?

```
kubectl create cm webapp-color-map --from-literal=APP_COLOR=darkblue
```

## How to update config map in Pod definition file?

```
take value from by running below command.
kubectl explain pods --recursive |grep envFrom |
```

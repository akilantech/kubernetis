## How to define volume common for all the containters?

```
  volumes:
  - name: cache-volume 
    emptyDir: {}
```

## How to define volume in container?

```
 - image: nginx
    name: nginx
    volumeMounts:
    - mountPath: /usr/share/nginx/html
      name: cache-volume
```

## How to write to volume in the container?

```
  containers:
  - image: busybox
    name: busybox
    args:
    - watch
    - -n1
    - echo
    - test >> /cache/index.html
    volumeMounts:
    - mountPath: /cache
      name: cache-volume
```
## What is the hostPath volume how it is different from emptyDir?

```
emtyDir will be deleted when Pod is deleted, but hostPath volume exposes nodes file directory.
It is basic type of persistent volume
```

## What is the purpose of Persistent Volume? How it is different from Volume created/linked in indivdual Pods ?

```
Persistent Volume is created by cluster administrator and provisioned. It will be assigned to the Pods based on the Persistent Claim Volumes.
Pod developer will not have any underlying knowledge on the volume.
```














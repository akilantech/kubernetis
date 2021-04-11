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

## What are access mode and their meaning?

```
RWO—ReadWriteOnce—Only a single node can mount the volume for reading and writing.
ROX—ReadOnlyMany—Multiple nodes can mount the volume for reading.
RWX—ReadWriteMany—Multiple nodes can mount the volume for both reading and writing.
```

## Create a busybox pod with 'sleep 3600' as arguments. Copy '/etc/passwd' from the pod to your local folder

```
kubectl run busybox --image=busybox --restart=Never -- sleep 3600
kubectl cp busybox:etc/passwd ./passwd # kubectl cp command
# previous command might report an error, feel free to ignore it since copy command works
cat passwd
```







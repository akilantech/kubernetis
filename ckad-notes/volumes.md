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


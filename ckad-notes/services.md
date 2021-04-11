## what is the default service type, if Service is not exposed?

```
ClusterIP
```

## How NodePort port number is assigned ?

```
The node’s IP address can be reached in combination with a port number in the range of 30000 and 32767, assigned automatically upon the creation of the Service
```

## How Service linked to Pods ?

```
Via Labels.

bash-3.2$ k describe svc nginx-ext
Name:                     nginx-ext
Annotations:              <none>
Selector:                 run=nginx



```



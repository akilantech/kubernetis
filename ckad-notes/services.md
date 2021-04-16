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

## What is NodePort service and how it works?

```
NodePort service helps to expose the pods or deployments to external world. It uses identifies resource by the label.
Note that expose the port only not the ip address.

k expose pod my-pod1 --type NodePort --dry-run=client --port 80 --target-port 80
Pods port is 80 and NodePort is 80

You can add external port in the template file as nodeport.

```





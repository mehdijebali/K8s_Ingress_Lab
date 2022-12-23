# K8s Ingress Lab 
In this Lab, we will manage access via Ingress K8s Object. 
Ingress in K8s manages external acces to **Services**. Apart from NodePort Service, ingress object is capable of many access options such as providing SSL termination, Load Balancing, Name Base Virtual Hosting.
K8s Cluster must have an ingress controller running in order to spin Ingress resource. In fact, Variety of Ingress Controller available in K8s to provide multiple mechanism for external access of Service. you can deploy any number of Ingress Controller.
Technically, ingress deﬁne a set of **Routing Rules**. Each Rule has a set of **Paths**, each with a **Backend**. As a result, the path will be routed to the associated Backend. If Service use **Named Port**, ingress can also use the port’s name to choose which port it will route.
```
apiVersion: networking.k8s.io/v1
kind: Ingress
metadata:
  name: nginx-rules
spec:
  rules:
  - host: nginx-official.example.com
    http:
      paths:
      - path: /
        pathType: Exact
        backend:
          service:
            name: nginx-official-service
            port:
              number: 80
```

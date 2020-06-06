# Easy deploy ingress traefik v1.7

Change your domain name in file **03-traefik-ingress.yml** in **10 line** and just execute the command

    $ kubectl apply -f .

To create ingress for your application, just create a new manifest for example

```
apiVersion: extensions/v1beta1
kind: Ingress
metadata:
  name: Ingress-app
  namespace: app
  annotations:
    kubernetes.io/ingress.class: traefik
spec:
  rules:
  - host: example.ru
    http:
      paths:
      - path: /
        backend:
          serviceName: app-service
          servicePort: 80
```

# Prometheus operator production ready

Requirements:
  - **GKE**
  - **Helm** is already installed in your local computer

## 1. Install Tiller
```
$ kubectl -n kube-system create serviceaccount tiller
$ kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
$ helm init --service-account tiller
```
## 2. Prometheus operator deploy
Ready persistent storage for prometheus with retention 30d and grafana

a) Create StorageClass ssd, namespace monitoring and persistent volume claim for grafana, just execute ```$ kubeclt apply -f .```

b) Deploy prometheus operator to your cluster using **Helm**:
    
    $ helm install stable/prometheus-operator --namespace monitoring -f values/prometheus-operator-values.yml
    
**Ready!** Just open local port ```$ kubectl port-forward service/<your-name-grafana> 8080:80 -n monitoring``` and go http://localhost:8080/

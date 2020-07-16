# Example deploy nginx monitoring using nginx-exporter

1. Edit file *01-nginx-exporter-deploy* and change args **nginx.scrape-uri** put your domain;
2. Edit file *02-nginx-service-monitor.yaml*, change **labels: -> release:** and put release your prometheus operator;
3. Deploy manifests ```$ kubectl apply -f .```
4. Configure your nginx, add new location:
```
location /stub_status/ {
        stub_status;
        allow 10.244.0.0/16;
        deny all;
      }
```
5. Load to Grafana my nginx dashboard ```nginx-dashboard-grafana.json```

**Ready!** Now you have monitoring nginx:)

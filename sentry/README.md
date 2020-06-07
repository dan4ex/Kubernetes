# Easy deploy sentry v9

Before the beginning:

1. If required сhange postgres db password in file 02-sentry-config.yml
2. Change your domain name in file 04-sentry-ingress.yml
3. Run command: ```kubectl apply -f .```
4. Go inside pod sentry-worker ```kubectl exec -it sentry-worker-pod -- /bin/bash``` and run command ```sentry upgrade```

**Performed! Sentry available on your domain**

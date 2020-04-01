# Network utils


### bash in network utils
```bash
kubectl run -it --rm nwu --restart=Never --image=kuritka/nwu -- bin/sh
```
to install whatewer you need run this:

```bash
apk add curl
```


### getting nslookup of service

```bash
kubectl run -it --rm nwu --restart=Never --image=nwu/kuritka -- nslookup rabbit-mq.onho-dev
```

where `rabbit-mq` is service name and `onho-dev` is namespace


### infinite sleep
```bash
kubectl run -it --rm nwu --restart=Never --image=kuritka/nwu -- /bin/sleep infinity
```

or

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: sleep
  namespace: mutant-test
  labels:
    app: sleep
spec:
  replicas: 1
  selector:
    matchLabels:
      app: sleep
  template:
    metadata:
      labels:
        app: sleep
    spec:
      containers:
        - name: sleep
          image: kuritka/nwu
          command: ["/bin/sleep","infinity"]
          imagePullPolicy: IfNotPresent
```

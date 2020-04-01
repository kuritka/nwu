#Network utils


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





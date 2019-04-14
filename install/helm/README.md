#### install helm

```
curl -Lo /tmp/helm-linux-amd64.tar.gz https://kubernetes-helm.storage.googleapis.com/helm-v2.13.1-linux-amd64.tar.gz
tar -xvf /tmp/helm-linux-amd64.tar.gz -C /tmp/
chmod +x  /tmp/linux-amd64/helm && sudo mv /tmp/linux-amd64/helm /usr/local/bin/
```

#### install tiller
kubectl apply -f tiller-rbac.yaml

#### init helm
helm init --service-account tiller --skip-refresh
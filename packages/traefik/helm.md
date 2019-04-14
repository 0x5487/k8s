helm install stable/traefik --name traefik --set dashboard.enabled=true,serviceType=NodePort,dashboard.domain=jason.local,rbac.enabled=true --version 1.66.0   --namespace kube-system

helm install stable/traefik --wait --name traefik --set dashboard.enabled=true,serviceType=NodePort,dashboard.domain=jason.local,rbac.enabled=true,metrics.prometheus.enabled=true  --namespace kube-system
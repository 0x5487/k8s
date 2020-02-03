### 安裝版本 k8s 1.15

   ```bash
   yum makecache fast
   yum install -y kubeadm-1.15.7 kubelet-1.15.7 kubectl-1.15.7 --disableexclude=kube*
   ```
   yum install -y kubectl-1.15.7 --disableexclude=kube*



kubeadm init \
  --kubernetes-version=v1.15.7 \
  --pod-network-cidr=10.244.0.0/16 \
  --apiserver-advertise-address=10.1.1.184



### 安裝 flannl 網路
kubectl apply -f  https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml



kubectl delete -f  https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml


### copy ca
mkdir -p $HOME/.kube
sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
sudo chown $(id -u):$(id -g) $HOME/.kube/config



### master accept job
kubectl taint nodes k8s04 node-role.kubernetes.io/master-
kubectl taint nodes k8s03 node-role.kubernetes.io/master-


### 修復 coreDNS loop 問題
kubectl edit cm coredns -n kube-system
delete ‘loop’ ,save and exit
kubctel delete pod coredns.... -n kube-system



cat <<EOF >> /etc/yum.repos.d/kubernetes.repo
exclude=kube*
EOF


### upgrade k8s
yum install -y kubeadm-1.13.5 kubelet-1.13.5 kubectl-1.13.5 --disableexclude=kube*
yum install kubeadm-1.13.5-0 --disableexclude=kube*

1. update kubeadm




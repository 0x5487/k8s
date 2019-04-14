1. Remove k8s completely

```
kubeadm reset 


# on debian base 
sudo apt-get purge kubeadm kubectl kubelet kubernetes-cni kube* 


#on centos base
sudo yum remove kubeadm kubectl kubelet kubernetes-cni kube*



# on debian base
sudo apt-get autoremove
#on centos base
sudo yum autoremove
 
sudo rm -rf ~/.kube
```
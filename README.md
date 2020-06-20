## k8s国内镜像维护

## v1.18.0

```sh
docker pull registry.cn-shanghai.aliyuncs.com/gocore/kube-apiserver:v1.18.0
docker pull registry.cn-shanghai.aliyuncs.com/gocore/kube-controller-manager:v1.18.0
docker pull registry.cn-shanghai.aliyuncs.com/gocore/kube-scheduler:v1.18.0
docker pull registry.cn-shanghai.aliyuncs.com/gocore/kube-proxy:v1.18.0
docker pull registry.cn-shanghai.aliyuncs.com/gocore/pause:3.2
docker pull registry.cn-shanghai.aliyuncs.com/gocore/etcd:3.4.3-0
docker pull registry.cn-shanghai.aliyuncs.com/gocore/coredns:1.6.7
docker pull registry.cn-shanghai.aliyuncs.com/gocore/flannel:v0.12.0-amd64
docker tag registry.cn-shanghai.aliyuncs.com/gocore/flannel:v0.12.0-amd64 quay.io/coreos/flannel:v0.12.0-amd64

# 初始化master
# --apiserver-advertise-address 参数改为master ip
kubeadm init --kubernetes-version=v1.18.0 --apiserver-advertise-address 192.168.137.3 --pod-network-cidr=10.244.0.0/16 --image-repository registry.cn-shanghai.aliyuncs.com/gocore
```

# k8s-svc-test

## create cluster with KIND

https://kind.sigs.k8s.io/docs/user/configuration/#kubeproxy-mode

iptables:

```sh
kind create cluster --config cluster/iptables.yaml
```

ipvs:
```sh
kind create cluster --config cluster/ipvs.yaml
```

## debug with Netshoot

enter k8s node network:
```sh
docker ps

docker run -it --net container:<node-ctr-id> --privileged=true nicolaka/netshoot
```

enter k8s pod network:
```sh
kubectl apply -f debug/debug.yaml
```

## net command

```sh
iptables-save

ipvsadm -l -n
```

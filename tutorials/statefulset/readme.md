检查他们在集群内部的 DNS 地址
```
[root@localhost statefulset]# kubectl run -i --tty --image busybox:1.28 dns-test --restart=Never --rm   
If you don't see a command prompt, try pressing enter.
/ # nslookup web-0.nginx
Server:    10.96.0.10
Address 1: 10.96.0.10 kube-dns.kube-system.svc.cluster.local

Name:      web-0.nginx
Address 1: 10.88.0.7 web-0.nginx.default.svc.cluster.local

```


qa: 动态提供 PersistentVolume

 扩展副本数为 5。
```
kubectl scale sts web --replicas=5
statefulset.apps/web scaled
```
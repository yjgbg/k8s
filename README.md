创建集群:
```shell
kind create cluster --config=kind.yaml
```

出于安全考虑，默认配置下Kubernetes不会将Pod调度到Master节点。如果希望将k8s-master也当作Node使用，可以执行如下命令：
```shell
kubectl taint node k8s-master node-role.kubernetes.io/master-
```
其中k8s-master是主机节点hostname如果要恢复Master Only状态，执行如下命令：
```shell
kubectl taint node k8s-master node-role.kubernetes.io/master=""
```

部署nginx-ingress-controller。必须部署，否则无法映射端口到外网

部署helloworld
会暴露endpoint: http://demo201202.yjgbg.life
```shell
kubectl apply -f hello-java.yaml
```
# 云原生示例

## 1. 内容
- [ ] Kubernets 自动部署、扩展和管理容器化应用程序
- [ ] CoreDNS 服务发现插件
- [ ] Calico网络插件
- [ ] Envoy 云原生高性能边缘/中间/服务代理
- [ ] Helm 包管理
- [ ] Prometheus 监控系统和时间序列数据库
- [ ] Fluentd统一日志层

## 2. 实战

### 安装Helm3
1. 使用脚本安装
```shell
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```
2. 分步安装
```shell
curl -fsSL -o get-helm-3.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
chmod 700 get-helm-3.sh
./get-helm-3.sh
```

### 安装istioctl
1. `curl -L https://istio.io/downloadIstio | sh -`

### 安装calico网络插件
1. [使用helm3安装calico](https://docs.projectcalico.org/getting-started/kubernetes/helm)
2. 安装 `helm install calico charts/calico/tigera-operator`
3. 观察 `watch kubectl get pods -n calico-system`

### 安装istio

1. 去[Github Release](https://github.com/istio/istio/releases/tag/1.11.0)界面下载最新的istio版本
2. 解压文件，helm charts 在manifests/charts目录内
3. 拷贝到本仓库
4. 按照 [istio/README-helm3.md](charts/istio/README-helm3.md) 文件指示进行安装

### 安装监控 kube-prometheus-stack
1. 添加 `helm repo add prometheus-community https://prometheus-community.github.io/helm-charts`
2. 下载 `helm pull prometheus-community/kube-prometheus-stack --version v17.2.2 --untar --untardir monitoring`
3. 安装 `helm install monitoring charts/monitoring/kube-prometheus-stack`

### 安装[kiali.io](https://kiali.io/documentation/v1.39/quick-start/)可视化Service Mesh

1. 添加 `helm repo add kiali https://kiali.org/helm-charts`
2. 下载 `helm pull kiali/kiali-server --untar --untardir charts/istio`
3. 安装 `helm install --namespace istio-system --set auth.strategy="anonymous" kiali-server charts/istio/kiali-server`


## 4. 操作技巧

**下载chart到本地**
[Helm Pull](https://helm.sh/zh/docs/helm/helm_pull/)
```shell
# 1. 添加repo
helm repo add projectcalico https://docs.projectcalico.org/charts
# 2. 列出本地repo
helm repo list
# 3. 下载repo到本地并解压
helm pull projectcalico/tigera-operator --version v3.20.0 --untar --untardir calico
```

## 5. 参考资料

1. [云原生全景图](https://landscape.cncf.io/)
2. [Kubernetes](https://kubernetes.io/zh/docs/home/)
3. [Helm v3包管理](https://helm.sh/zh/)
4. [Prometheus](https://prometheus.io/)
5. [Envoy](https://www.envoyproxy.io/)
6. [Calico](https://docs.projectcalico.org/getting-started/kubernetes/helm)
7. [语义化版本号](https://semver.org/lang/zh-CN/)

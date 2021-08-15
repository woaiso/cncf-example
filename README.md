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
使用脚本安装
```shell
curl https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 | bash
```

## 4. 操作技巧

**下载chart到本地**
[Helm Pull](https://helm.sh/zh/docs/helm/helm_pull/)
```shell
# 1. 添加repo
helm repo add projectcalico https://docs.projectcalico.org/charts
# 2. 列出本地repo
helm repo list
# 3. 下载repo到本地并解压
helm pull projectcalico/tigera-operator --version v3.20.0 --untar --untar calico
```

## 5. 参考资料

1. [云原生全景图](https://landscape.cncf.io/)
2. [Kubernetes](https://kubernetes.io/zh/docs/home/)
3. [Helm v3包管理](https://helm.sh/zh/)
4. [Prometheus](https://prometheus.io/)
5. [Envoy](https://www.envoyproxy.io/)
6. [Calico](https://docs.projectcalico.org/getting-started/kubernetes/helm)
7. [语义化版本号](https://semver.org/lang/zh-CN/)

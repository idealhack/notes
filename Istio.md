# Istio

## Overview

- [Istio](https://istio.io/)
- [istio/istio: Sample code, build and tests and governance material for the Istio project.](https://github.com/istio/istio)
- [Istio官方文档中文版](https://doczhcn.gitbooks.io/istio/content/)

## Install

- [Istio / Quick Start](https://istio.io/docs/setup/kubernetes/quick-start.html)

### Caution

1. Append `--feature-gates=AllAlpha=true` flag to `/etc/systemd/system/kubelet.service.d/10-kubeadm.conf`
2. Append `--runtime-config=admissionregistration.k8s.io/v1alpha1` flag to `/etc/kubernetes/manifests/kube-apiserver.yaml`
3. `sudo systemctl daemon-reload && sudo systemctl restart kubelet`

## Resources

- [Istio：用于微服务的服务啮合层](http://www.infoq.com/cn/news/2017/05/istio)
- [Qcon2017实录|Service Mesh：下一代微服务（附PPT下载）](https://mp.weixin.qq.com/s/KeHX4Ybh3Tc_3xEQlCiS5w)

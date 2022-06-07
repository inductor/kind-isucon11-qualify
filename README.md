# kind-isucon

ISUCON 11予選の環境をKinD(Kubernetes in Docker)上に作成するためのリポジトリです。クラスタ作成の利便性からkindの名前を借用していますが、仕組み的にはほかのKubernetesディストロ(GKE、EKS、kubeadmなど)でも同様に動くように作られています。

- [Docker CE](https://docs.docker.com/)(Windows/macOSのデスクトップ版だとVMのリソースを制限できるので便利ですが、Linux版でも普通に動かせます)
- [kind](https://kind.sigs.k8s.io/)
- [Helm](https://helm.sh/)

## kindクラスターの作成

1. リポジトリをforkしてcloneします。

2. Project rootにてkindクラスターを作成します。

```sh
kind create cluster --config kind-config/cluster.yaml
```

3. HelmにてArgo CDをインストールします。

```sh
helm install argocd --create-namespace -n argocd argo/argo-cd
```

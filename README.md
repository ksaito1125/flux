# flux

```
kubectl create ns flux
curl -Ls -o flux https://github.com/fluxcd/flux/releases/download/1.17.0/fluxctl_linux_amd64
chmod  +x fluxctl
sudo mv fluxctl /usr/local/bin/fluxctl
export GHUSER=ksaito1125
fluxctl install --git-user=${GHUSER} --git-email=${GHUSER}@users.noreply.github.com --git-url=git@github.com:${GHUSER}/flux-get-started --git-path=namespaces,workloads --namespace=flux | kubectl apply -f -
kubectl -n flux rollout status deployment/flux
fluxctl identity --k8s-fwd-ns flux
```

## 参考

[Get started with Flux](https://github.com/fluxcd/flux#get-started-with-flux)

以上

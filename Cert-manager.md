<p align="center">
<img src="https://www.authelia.com/images/logos/haproxy.png" height="150" style="margin-right: 10px;">
<img src="https://github.com/netdata/netdata/blob/941fff633212dc0034a08148622fd0e4023f07e2/web/gui/v2/static/img/logos/os/kubernetes.svg" height="75" style="margin-right: 10px;">
<img src="" height="150" style="margin-right: 10px;">
    
</p>

## Quick Reference for Let's Encrypt Cert-Manager

#### Haproxy Configuration
```
    frontend http_front
      bind *:443
      mode tcp
      option tcplog
      default_backend http_back

    backend http_back
      mode tcp
      balance roundrobin
      server kworker1 <kworker1-ip>:443
      server kworker2 <kworker2-ip>:443
```

#### Helm Installation
```
    wget https://get.helm.sh/helm-v2.14.1-linux-amd64.tar.gz
    tar zxf helm*gz
    sudo cp linux-amd64/helm /usr/local/bin/
    rm -rf helm* linux-amd64
    kubectl -n kube-system create serviceaccount tiller
    kubectl create clusterrolebinding tiller --clusterrole cluster-admin --serviceaccount=kube-system:tiller
    helm init --service-account tiller
```
*Wait for the tiller component to be active.*

#### Cert-Manager Setup
```
    kubectl apply -f https://raw.githubusercontent.com/jetstack/cert-manager/release-0.8/deploy/manifests/00-crds.yaml
    helm repo add jetstack https://charts.jetstack.io
    helm install --name cert-manager --namespace cert-manager jetstack/cert-manager
```
*Wait for the cert-manager pods to be active.*
```
    kubectl create -f https://raw.githubusercontent.com/justmeandopensource/kubernetes/master/yamls/cert-manager-demo/ClusterIssuer.yaml
```    

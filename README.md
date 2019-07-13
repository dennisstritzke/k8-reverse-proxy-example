# Example Reverse Proxy
This repository demonstrates how to use Kubernetes and the Nginx Ingress to proxy a legacy website, while not having
access to the server hosting the website. Find the motivation for this repository in my blog post
[Preserving the internet of 2005](https://stritzke.me/preserving-the-internet-of-2005/).

## Run
If you have an Ingress controller available consider changing the DNS names used within the Kubernetes resources.
Otherwise you could just use `kubectl port-forward <pod> 8080:80` to access the proxy via `http://localhost:8080`.

```
kubectl create ns example-proxy
kubectl apply -f kubernetes/ -n example-proxy
```

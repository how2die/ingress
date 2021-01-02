# Ingress

We use the [NGINX Ingress Controller](https://kubernetes.github.io/ingress-nginx/).

To deploy the controller, run:

`kubectl apply -f https://raw.githubusercontent.com/kubernetes/ingress-nginx/controller-v0.43.0/deploy/static/provider/cloud/deploy.yaml`

Remember to route HTTP (80) and HTTPS (443) traffic to the ports exposed by ingress-nginx-controller
These can be found using `kubectl get services --all-namespaces`

## Use cert-manager to manage HTTPS

Install CustomResourceDefinitions and cert-manager:

`kubectl apply -f https://github.com/jetstack/cert-manager/releases/download/v1.1.0/cert-manager.yaml`

To deploy ClusterIssuer using Let's Encrypt, run:

`kubectl apply -f cert-issuer.yaml`

## Apply ingresses

Run:

`kubectl apply -f ingress.yaml`

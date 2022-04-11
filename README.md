# Configure TLS/SSL certificate using cert-manager

### Pre-requisties

1. Any of the ingress controller with HTTPS port enabled and you should know the ```ingress-class``` name.
2. Knowledge of helm-charts

## Install Cert-manager

    1. Install custom-crds for the cert-manager.

        kubectl apply --validate=false -f https://github.com/jetstack/cert-manager/releases/download/v1.0.4/cert-manager.crds.yaml

    2. Install cert-manager using helm
        
        helm install cert-manager cert-manager/ --namespace cert-manager --create-namespace

## Now apply cluster issuer after verifying the cert-manager is working.

    1. kubectl apply -f issuers/letsencrypt-prod.yaml

## Now configure the ingress to use this cluster issuer.

# For more tutorial, read out this blog.

    https://blog.knoldus.com/configure-ssl-certificate-with-cert-manager-on-kubernetes/ 
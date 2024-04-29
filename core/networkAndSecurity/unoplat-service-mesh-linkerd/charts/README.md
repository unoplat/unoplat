# unoplat-service-mesh-linkerd
Linkerd for unoplat

# installation


## Linkerd Cli Installation

curl --proto '=https' --tlsv1.2 -sSfL https://run.linkerd.io/install | sh

# Generate certificates on own

1. brew install step
2. step ca init --name "MyCA" --provisioner admin --dns localhost --address ":8443" --password-file <(echo "password")
3. step certificate create --profile root-ca "identity.linkerd.cluster.local" root.crt root.key (Root Certificate)
4. step certificate create --profile intermediate-ca --ca root.crt --ca-key root.key "identity.linkerd.cluster.local" issuer.crt issuer.key (Intermediate Certificate)
5. helm repo add jetstack https://charts.jetstack.io
6. helm repo update
7. helm install \
  cert-manager jetstack/cert-manager \
  --namespace unoplat-service-mesh \
  --create-namespace \
  --version v1.13.1 \
  --set installCRDs=true
8. kubectl create secret tls unoplat-service-mesh-ca-secret --cert=root.crt --key=root.key -n unoplat-service-mesh
9. kubectl create -f code/base-project/cluster-issuer.yaml -n unoplat-service-mesh
10. kubectl create -f code/base-project/certificate.yaml -n unoplat-service-mesh


## Linkerd installation

1. kubectl annotate namespace unoplat-service-mesh linkerd.io/inject=disabled
2. helm repo add linkerd https://helm.linkerd.io/stable
3. helm repo update
4. helm install unoplat-linkerd-crds linkerd/linkerd-crds -n unoplat-service-mesh --version 1.8.0
5. (Skip this as of now)helm install unoplat-linkerd-cni -n unoplat-service-mesh linkerd/linkerd2-cni 
6. helm install unoplat-linkerd-control-plane . -n unoplat-service-mesh \
  --set-file identityTrustAnchorsPEM=root.crt \
  --set-file identity.issuer.tls.crtPEM=issuer.crt \
  --set-file identity.issuer.tls.keyPEM=issuer.key \
  --set cniEnabled=false \
  -f values.yaml 
7. install cli ->  curl -sL https://run.linkerd.io/install | sh
  

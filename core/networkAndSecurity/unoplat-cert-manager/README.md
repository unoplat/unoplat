1. brew install step
2. step ca init --name "MyCA" --provisioner admin --dns localhost --address ":8443" --password-file <(echo "password")
3. step certificate create --profile root-ca "identity.linkerd.cluster.local" root.crt root.key (Root Certificate)
4. step certificate create --profile intermediate-ca --ca root.crt --ca-key root.key "identity.linkerd.cluster.local" issuer.crt issuer.key (Intermediate Certificate)
5. helm repo add jetstack https://charts.jetstack.io
6. helm repo update
7. helm install \
  cert-manager . \
  --namespace unoplat-service-mesh \
  --create-namespace \
  --version v1.13.1 \
  --set installCRDs=true
1. kubectl create secret tls unoplat-service-mesh-ca-secret --cert=root.crt --key=decrypted.key -n unoplat-service-mesh
2. kubectl create -f code/base-project/cluster-issuer.yaml -n unoplat-service-mesh
3.  kubectl create -f code/base-project/certificate.yaml -n unoplat-service-mesh

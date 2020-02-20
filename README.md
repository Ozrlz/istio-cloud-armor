## Create secrets for certs

kubectl create secret tls cert1 --namespace istio-system --cert nginx.ozrlz.com.crt --key nginx.ozrlz.com.key

kubectl create secret tls cert2 --namespace istio-system --cert flask.ozrlz.com.crt --key flask.ozrlz.com.key

## PR where planned to add HC support on BackendConfig CRD
https://github.com/kubernetes/ingress-gce/pull/1010

## Generate manifest 
istioctl manifest generate --set installPackagePath=./charts --filename=./profile.yaml > manifest.yaml

Once Istio installed and secret for certs created, apply flask and nginx apps and Ingress resource as well. Before LB is good, you need to modify the healthcheck used for the istio-ingressgateway backend (create a fw rule on port 30020 and point it to /healthz/ready)
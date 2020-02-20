1.- Create terraform code to provision L7 GLB
2.- Create terraform code to provision the cloud armor policies
3.- Investigate what are the other ports of the istio-ingressgateway used for 
4.- Setup the istio helm chart to deploy the http/https (80,443) traffic using a GKE ingress (with an special node port) and the rest of the ports using an internal Load balancer with an static IP
5.- Pray (Dorimé)
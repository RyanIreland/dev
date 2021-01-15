# First time GCP Deployment Steps
This page outlines the steps to deploy app on a kubernetes cluster on GKE.

# GCP
- [Create GCP billed account](https://console.cloud.google.com/billing/01D4EF-77D620-DAFCAA?project=utopian-theater-297420)
- [Google Business
Create a business](https://business.google.com/site/l/15307595727785047865?hl=en)

# GKE
- [Create a Kubernetes cluster](https://console.cloud.google.com/kubernetes/list?project=utopian-theater-297420&folder=&organizationId=)

### Make cluster available to local control with kubectl
> $ gcloud kubectl init
>
> $ gcloud container clusters get-credentials my-first-cluster-1 --zone us-central1-c --project utopian-theater-297420

# Deploy App
- Deploy rnr-rest-api & rnr-ui
> 	$ kubectl apply -f rnr-rest-api.yaml
> 
> 	$ kubectl apply -f rnr-rest-api-service.yaml
> 
> 	$ kubectl apply -f rnr-ui.yaml
> 
> 	$ kubectl apply -f rnr-ui-service.yaml
- Services now exposed with NodePorts 3600:3600 & 3000:3000
- From GKE console, select both services and create rnr-ingress with default backed rnr-ui-service
- (add /rnr/auth & /rnr/users paths to rnr-rest-api-service)
- Now from command line, get the ingress yaml
> 	$ kubectl get ingress -o yaml > rnr-ingress.yaml
- Can now customize rnr-ingress.yaml
- Add annotation to rnr-ingress yaml:
> 	$ kubernetes.io/ingress.global-static-ip-name: "web-static-ip"
- Update the ingress 
> 	$ kubectl apply -f rnr-ingress.yaml

# Google Domain
- Create a static IP
> gcloud compute addresses create web-static-ip --global

- [Buy a domain "rabbitnroo.com"](https://domains.google.com/registrar/search?searchTerm=ren.com&hl=en&_ga=2.67240145.1107454859.1610462061-863361608.1610462061#)

- [Create a google DNS zone "rabbitnroo"](https://domains.google.com/registrar/rabbitnroo.com/dns?_ga=2.42768225.599502862.1610551551-863361608.1610462061)

- Verify DNSSEC is enabled in console for DNS
- Add static ip registered Host records for rabbitnroo.com & www.rabbitnroo.com
- Add Synthetic record:
> 	www.rabbitnroo.com → 34.120.6.200
> 	Permanent redirect (301), Do not forward path, Enable SSL
- In rnr-ingress.yaml:
- Map static IP to domain with annotation
> 	$ kubernetes.io/ingress.global-static-ip-name: 'web-static-ip'
- Map domain with rule
> 	- host: www.rabbitnroo.com
- Add cert annotation
> 	networking.gke.io/managed-certificates: 'rnr-cert'
- Apply both of the above
> 	$ kubectl apply -f rnr-cert.yaml
> 	$ kubectl apply -f rnr-ingress.yaml
- Get details
> 	$ kubectl describe managedcertificate rnr-cert
>  $ gcloud beta compute ssl-certificates list

# Notes
- [View load balancer](https://console.cloud.google.com/net-services/loadbalancing/loadBalancers/list?project=utopian-theater-297420)
- [Details](https://cloud.google.com/kubernetes-engine/docs/concepts/ingress)

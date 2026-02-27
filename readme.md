This Repo is for Kubernetes for Research-paper project

Current- 
1. Added Support for www.lukkyy.online
2. Removed Publically Exposed API Keys.
<!-- Please Run all yamls (paste following codes) -->

kubectl delete namespace dev-research-app

kubectl apply -f namespace.yaml

kubectl apply -f secret/

kubectl apply -f mongo/

kubectl apply -f backend/

kubectl apply -f frontend/

kubectl apply -f ingress/

<!-- x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x -->

<!-- To Check All Resources -->
kubectl get pods -n dev-research-app

kubectl get svc -n dev-research-app

kubectl get ingress -n dev-research-app

kubectl get hpa -n dev-research-app


<!-- To Verify DNS -->
nslookup lukkyy.online

it should return ec2 public ip
then

curl http://lukkyy.online

Look Address Column
kubectl get ingress -n dev-research-app

This Repo is for Kubernetes for Research-paper project

Current- Ingress Was Being Applied Before namespace.yaml thus creating an issue, (Ingress.yaml was indirectly trying to create a new namespace). So, To solve this issue created a DIR ingress.

Created a Separeate DIR For Secret.yaml.

Modified Mongo-Service Type from ClusterIp: None to type: ClusterIP

Renamed namespace.yml to namespace.yaml (K8s Checks it Exactly, This was Causing Issue Before).

<!-- Create DNS Records -->
Type: A
Host: @
Points to: <EC2 public IP>
TTL: 600


Type:A
Host: www
Points to: <EC2 public IP>



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

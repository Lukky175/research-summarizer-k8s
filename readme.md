This Repo is for Kubernetes for Research-paper project

Current- Added Resource Block In Deployment Of Both FrontEnd & Backend. (For Using HPA)

<!-- Please Run all yamls (paste following codes) -->

kubectl apply -f namespace.yaml
kubectl apply -f secret.yaml
kubectl apply -f ingress.yaml

cd mongo
kubectl apply -f mongo-pvc.yaml
kubectl apply -f mongo-deployment.yaml
kubectl apply -f mongo-service.yaml
cd ../


cd backend
kubectl apply -f backend-deployment.yaml
kubectl apply -f backend-service.yaml
kubectl apply -f hpa-backend.yaml
cd ../

cd frontend
kubectl apply -f frontend-deployment.yaml
kubectl apply -f frontend-service.yaml
kubectl apply -f hpa-frontend.yaml
cd ../


<!-- x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x-x -->

<!-- To Check All Resources -->
kubectl get pods -n dev-research-app

kubectl get svc -n dev-research-app

kubectl get ingress -n dev-research-app

kubectl get hpa -n dev-research-app

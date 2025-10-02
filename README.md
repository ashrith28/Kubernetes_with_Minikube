# TASK 5 - Kubernetes with Minikube

## Objective
Deploy a simple nginx application on a local Kubernetes cluster using Minikube. Provide YAML manifests, verification commands, and screenshots.

## Files
- `deployment.yaml` — Deployment manifest (nginx).
- `service.yaml` — Service manifest (NodePort).

## Steps I followed
1. Started Minikube:
   `minikube start`
2. Applied manifests:
   `kubectl apply -f deployment.yaml`
   `kubectl apply -f service.yaml`
3. Verified resources:
   `kubectl get pods,svc,deployment`
4. Scaled deployment:
   `kubectl scale deployment/demo-nginx-deployment --replicas=4`
5. Performed a rolling update:
   `kubectl set image deployment/demo-nginx-deployment nginx=nginx:1.23.4`
   `kubectl rollout status deployment/demo-nginx-deployment`
6. Collected screenshots and logs as required.

## How to run locally
1. Install Minikube and kubectl.
2. `minikube start`
3. `kubectl apply -f deployment.yaml`
4. `kubectl apply -f service.yaml`
5. `minikube service demo-nginx-service`

## Notes
- Service uses NodePort (30080) so you can access the app at the URL returned by `minikube service --url`.
- Replace `nginx:stable` with a custom image if you want to demo your own app.

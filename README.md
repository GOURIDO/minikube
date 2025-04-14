Minikube NGINX Deployment on Kubernetes-
This project demonstrates how to deploy a simple NGINX application on a local Kubernetes cluster using Minikube. The setup includes creating and applying deployment and service YAML files, scaling the deployment, and verifying the setup using kubectl commands.
Project Structure
minikube/
├── deployment.yaml          # Defines the NGINX deployment
├── service.yaml             # Exposes the deployment via ClusterIP service
├── screenshots/             # Contains screenshots of each step
│   ├── Screenshot (1).png   # Initial apply of deployment and service
│   ├── Screenshot (2).png   # Checking pod status
│   ├── Screenshot (3).png   # Attempt to scale with incorrect name
│   ├── Screenshot (4).png   # Getting deployment name
│   ├── Screenshot (5).png   # Successful scaling of deployment
│   └── Screenshot (6).png   # Final pod status with 3 replicas
Setup Instructions
1. Start Minikube
Ensure Minikube is installed on your machine. Then start your local Kubernetes cluster with the following command:
minikube start
2. Apply Deployment and Service
Navigate to the minikube directory and apply the configuration files:
kubectl apply -f deployment.yaml
kubectl apply -f service.yaml
This will create the NGINX deployment and expose it using a ClusterIP service.
3. Check Running Pods
Verify that the pod has been created and is running:
kubectl get pods
You should see one NGINX pod listed.
4. Get Deployment Name
If you need to interact with the deployment (for example, to scale it), get the exact deployment name:
kubectl get deployments
5. Scale the Deployment
Use the deployment name to scale the number of replicas. For example, to scale to 3 replicas:
kubectl scale deployment my-nginx-deployment --replicas=3
Replace my-nginx-deployment with the actual name of your deployment.
6. Verify Scaling
Check that the number of pods has increased:
kubectl get pods
You should now see three NGINX pods

*Screenshots
1.The screenshots/ folder includes six screenshots that demonstrate each step of the process:

2.Applying the deployment and service

3.Viewing the initial pod

4.Attempting to scale using an incorrect name

5.Checking the actual deployment name

6.Scaling the deployment

7.Verifying that three pods are running

*Additional Notes
Make sure you're in the correct directory when running kubectl apply.

If an error occurs while scaling, confirm the deployment name using kubectl get deployments.

Only deployment objects can be scaled—not individual pods

*Tech Stack
Minikube – For running a local Kubernetes cluster

Kubernetes – Container orchestration platform used to deploy and manage applications

kubectl – CLI tool to interact with the Kubernetes cluster

NGINX – Web server deployed in the Kubernetes cluster

YAML – Configuration language used to define Kubernetes objects

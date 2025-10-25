Technical Report: Kubernetes Application Deployment

Project Title:

Application Deployment to Kubernetes Cluster

Author:

Joy Brown — Cloud DevOps Engineer (AltSchool Africa Project)


---

1. Introduction

This project demonstrates the deployment of a containerized application to a Kubernetes (K8s) cluster. The goal is to showcase how to automate the deployment and scaling of modern microservices using Kubernetes orchestration principles.

The deployment was carried out as part of a cloud engineering project, focusing on real-world DevOps tools and workflows.


---

2. Objectives

Deploy a sample web application to a Kubernetes cluster.

Manage pods, services, and deployments using YAML manifests.

Expose the application externally via a LoadBalancer service.

Implement best practices for scalability and high availability.

Use GitHub for version control and project documentation.



---

3. Tools and Technologies

Tool/Service	Purpose

Kubernetes (K8s)	Container orchestration
Docker	Containerization
AWS EKS / Minikube / Kind	Kubernetes cluster environment
kubectl	Kubernetes CLI for cluster management
Terraform (optional)	Infrastructure provisioning
AWS CLI	Cloud service configuration
Git & GitHub	Version control and collaboration
YAML	Configuration language for manifests



---

4. Architecture Overview

The architecture consists of:

A Kubernetes cluster (master & worker nodes).

A Deployment object that manages application pods.

A Service (LoadBalancer type) to expose the app to the internet.

(Optional) Ingress controller for routing traffic to services.


User --> LoadBalancer Service --> Kubernetes Cluster --> Application Pods --> Containerized App


---

5. Deployment Steps

1. Create Docker Image

Built Docker image of the application.

Tagged and pushed the image to Docker Hub or AWS ECR.



2. Set Up Kubernetes Cluster

Used Minikube (local) or AWS EKS (cloud) for cluster setup.

Verified cluster nodes using:

kubectl get nodes



3. Deploy Application

Created Kubernetes manifests:

deployment.yaml — defines replicas, image, and container ports.

service.yaml — exposes the app using LoadBalancer.


Applied manifests:

kubectl apply -f deployment.yaml
kubectl apply -f service.yaml



4. Verify Deployment

kubectl get pods
kubectl get svc

Confirmed running pods and accessible external IP.



5. Access Application

Accessed the app using the external LoadBalancer or Minikube service URL.





---

6. Results

✅ The application was successfully deployed and made accessible via the Kubernetes cluster.
✅ All pods were running in the “Running” state.
✅ LoadBalancer/NodePort exposed the service to external users.


---

7. Challenges & Solutions

Challenge	Solution

Image pull issues	Ensured correct Docker image name & authentication
Service not reachable	Verified ports and service type configuration
Pod crash loops	Checked logs using kubectl logs and fixed YAML configs



---

8. Conclusion

The project successfully demonstrated container orchestration using Kubernetes. It enhanced understanding of deployment automation, scalability, and container networking in real-world environments.

Future improvements could include adding:

Helm charts for easier deployment.

CI/CD automation using GitHub Actions.

Monitoring with Prometheus and Grafan.

Kubernetes Documentation

Docker Documentation

AWS EKS Guide

Minikube

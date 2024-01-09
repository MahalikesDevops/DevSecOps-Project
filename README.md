# MyProjects
Cloud Native Monitoring application
====================================
1.	How to create a monitoring application in Python using flask
2.	Start by building the application and then containerize it using Docker
3.	Create a docker file, build the image, and run the container locally
4.	Then create an ECR using the Python boto3 module, in ECR, we will push the docker image to store, retrieve, and use the docker images in a secure and efficient manner
5.	Next in the deployment phase we will create an elastic Kubernetes cluster with nodes and deploy the application on Kubernetes, we will create deployment and service using Python, so that our application can be accessed from the internet that is deployed in Kubernetes.
   
Tools: Python, Kubernetes, Docker, Amazon ECR, Python+boto3


Deploy Netflix Clone on Kubernetes using Jenkins
================================================
DevSecOps stands for development, security, and operations. It's an approach to culture, automation, and platform design that integrates security as a shared responsibility throughout the entire IT lifecycle.
1.	First, we create an EC2 instance and host an application locally using a Docker container.
2.	Then we are integrating with SonarQube and Trivy to securely host the application manually
3.	Once this is done, we are going to automate this process of ec2 creation, and securely hosting using Jenkins.
4.	Then we are going to integrate this with Prometheus and Grafana to monitor our ec2 instance and Jenkins*(CPU, RAM, successful/failed jobs, etc) and get an email notification using SFTP.
5.	After this we are going to deploy our application in Kubernetes using ArgoCD which is a GitOps tool and we will have monitoring (Prometheus and Grafana) on our Kubernetes cluster which is going to be installed using Helm charts 
6.	Finally, we have our application deployed on Cloud.

Tools: EC2, Jenkins, ArgoCD and Helm, Prometheus and Grafana (Monitoring), SonarQube and Trivy(Security), Docker, Kubernetes

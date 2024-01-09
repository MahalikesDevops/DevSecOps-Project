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

----------------------------------------------------------------------------------------------------------------------------------------

Requirements:
1.	T2.large instance with Jenkins, SonarQube, Trivy in AWS:
   
      •	The reason we are using T2, large is that we will be using so many plugins, so we need a server compatible with that.
      
      •	So in your AWS Account-> create instance-> name (Netflix-Jenkins)-> Ubuntu(version22)-> T2.large-> Create key if required; Linux (.pem), for windows (.ppk)to connect using putty-> leave at default VPC and subnet-> for security group, we will create one that has only the ports we need enable to make it secure-> so allow only SSH, HTTPS (to connect Jenkins with docker) and HTTP for now-> storage 25GB (cause we need large server)-> Launch instance
      
      •	Since it's a lengthy project lets have an elastic IP setup so that our public IPV4 address would remain the same. So, in EC2 management console-> under security-> elastic IP-> allocate elastic IP-> set region and create->give a name for elastic IP (Netflix-EIP)->Associate elastic IP -> select the instance-> Associate
      
      •	Select instance-> connect-> EC2-instance connect-> and enter the below command to update packages.
      
      •	Clone the repository by using the below command:

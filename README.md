# Brain-Tasks-App# AWS DevOps Deployment


This project gave me practical experience in deploying a React application on AWS using Docker, Amazon ECR, Amazon EKS and Kubernetes. I learned how to create and test Docker images, configure Kubernetes deployments and services, and troubleshoot connectivity issues using logs and Kubernetes commands. I also gained a better understanding of AWS IAM, LoadBalancers, GitHub integration and CI/CD using CodeBuild and CodePipeline. Overall, the project helped me understand how different DevOps tools work together in a real deployment and improved my confidence in troubleshooting and managing cloud-based applications.

I attached all the snippets in the repository and I'll attach the document as well.

Challenges Faced During the Project:

AWS IAM Permissions One of the initial challenges I faced was understanding the AWS permissions required for different services. I had issues while accessing ECR from the EC2 instance because the required permissions were not available. I resolved this by attaching the appropriate IAM role to the EC2 instance and verifying the access using AWS CLI.

Docker Configuration I faced some challenges while creating and configuring the Docker image for the application. I had to understand how Nginx serves the React application and how to configure it to listen on port 3000. After making the required changes to the Dockerfile and Nginx configuration, I tested the container locally to make sure the application was working correctly.

Understanding the Repository Structure While working on the project, I noticed that the dist directory was not present in the repository on the EC2 instance. Initially, I was unsure whether I needed to build the React application again. After checking the Docker container and application logs, I confirmed that the application files were already being served correctly by Nginx.

EKS Networking Setting up the EKS environment was another area where I faced some difficulty. I had to understand how the EKS cluster, worker nodes, pods, Kubernetes Services and AWS networking work together. Checking the nodes and Kubernetes resources helped me understand how traffic moves from the AWS infrastructure to the application pods.

LoadBalancer Troubleshooting The biggest troubleshooting challenge was related to the Kubernetes LoadBalancer. The application was running correctly inside the pods, but I was initially unable to access it through the external LoadBalancer. I checked the Service configuration, NodePort, endpoints and AWS LoadBalancer settings and found a port mismatch. After correcting the Service configuration, the LoadBalancer was able to forward traffic correctly to the application.

Kubernetes Troubleshooting I also had to spend some time understanding how to troubleshoot Kubernetes issues. I used commands such as kubectl get pods, kubectl get svc, kubectl get endpoints, kubectl describe and kubectl logs to check the status of different resources. This helped me identify whether an issue was related to the pod, Service or external networking.

Git and GitHub Integration I faced some initial challenges while configuring Git and pushing the project from the EC2 instance to GitHub. I also received a Git user identity warning because Git automatically configured the username and email based on the EC2 instance. After configuring Git and authenticating with GitHub, I was able to push the project successfully to the main branch.

CI/CD Configuration Understanding the complete CI/CD flow was another learning experience. I had to understand how a change pushed to GitHub triggers CodePipeline, how CodeBuild builds the Docker image, how the image is pushed to ECR and how the application is eventually deployed to EKS. Testing the pipeline with a small README change helped me understand this flow practically.

Monitoring and Logging During troubleshooting, application logs were very useful in identifying where the problem was occurring. I checked the Kubernetes and Nginx logs to verify whether the application was receiving requests. The HTTP 200responses in the Nginx logs confirmed that the application itself was working, which helped me focus on the infrastructure and LoadBalancer configuration.

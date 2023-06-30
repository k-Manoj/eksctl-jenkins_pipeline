# eksctl-jenkins_pipeline
Deploy Springboot Microservices App into Amazon EKS Cluster using Jenkins Pipeline | Containerize Springboot App and Deploy into EKS Cluster using Jenkins Pipeline

### for latest version of installing eksctl - 
https://github.com/weaveworks/eksctl
### install jenkins
https://www.jenkins.io/doc/book/installing/linux/

### install docker and kubectl and git 
yum install docker -y ; yum install git -y
### install awscli
create a cluster using - eksctl create cluster --name demo-eks --region us-east-1 --nodegroup-name my-nodes --node-type t3.small --managed --nodes 2 
                        - eksctl get cluster --name demo-eks --region us-east-1
                        - aws eks update-kubeconfig --name demo-eks --region us-east-1
                        - you can view the kubeconfig file by entering the below command: cat  /var/lib/jenkins/.kube/config
### check for jenkins permissions to access docker: 
Now Login to Jenkins EC2 instance, execute below commands:
#Add jenkins user to Docker group
sudo usermod -a -G docker jenkins
#Restart Jenkins service
sudo service jenkins restart
#Reload system daemon files
sudo systemctl daemon-reload
#Restart Docker service as well
sudo service docker stop
sudo service docker start

### install Helm aws eks update-kubeconfig --name demo-eks --region us-east-1

1.curl -fsSL -o get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3
2.sudo chmod 700 get_helm.sh
3.sudo ./get_helm.sh
4.helm version --client

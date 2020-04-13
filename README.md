# Udacity - Cloud DevOps Engineering Nanodegree - Capstone Project


## Project Task:
In this project I will apply the skills and knowledge which were developed throughout the Cloud DevOps Nanodegree program. These include:

   - Working in AWS
   - Using Jenkins to implement CI/CD
   - Building pipelines
   - Building Kubernetes clusters
   - Building Docker containers in pipelines
   
#### Project Requirement:

* EC2
* Jenkins/ BlueOcean
* pip
* Docker
* kubectl
* awscli
* eksctl

## Steps:

### Step 1: Setup of EC2 for Jenkins
   - Create new EC2 instance in AWS
   - Install Jenkins in EC2 instance
#### Setup of EC2 for Jenkins
##### Install Jenkins in EC2:
      1.- Install JDK
         ```
         $ sudo apt update
         $ sudo apt install default-jre            
         $ sudo apt install openjdk-8-jre-headless
         ```
      2.- Install Jenkins
         ```
         $ sudo apt update
         $ wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
         $ sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
         $ sudo apt install jenkins
         $ sudo usermod -a -G docker jenkins
         $ sudo systemctl start jenkins
      ```
      3.- Jenkins Plugins (Blue Ocean and AWS)
      
##### Install tools needed for the pipelines
##### Docker
      ```
      $ sudo apt update
      $ sudo apt install apt-transport-https ca-certificates curl software-properties-common
      $ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
      $ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
      $ sudo apt  install docker.io
      $ sudo chmod 666 /var/run/docker.sock
      $ sudo systemctl restart docker
       ```
##### Python
      ```
      $ sudo apt update
      $ sudo apt install python-pip
      $ sudo apt install python3-pip
      ```
##### awscli
      ```
      $ pip3 install --upgrade --user awscli
      $ sudo apt install awscli
      $ aws configure
         AWS Access Key ID [None]: XXXXXXXXXXXXXXXXXXXX
         AWS Secret Access Key [None]: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
         Default region name [None]: us-east-2
         Default output format [None]: json
      ```

##### eksctl
      ```
      $ sudo apt update
      $ curl --silent --location "https://github.com/weaveworks/eksctl/releases/download/latest_release/eksctl_$(uname -s)_amd64.tar.gz"        | tar xz -C /tmp
      $ sudo mv /tmp/eksctl /usr/local/bin
      ```
##### aws-iam-authenticator
      ```
      $ sudo apt update
      $ curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/aws-iam-                  authenticator
      $ chmod +x ./aws-iam-authenticator
      $ mkdir -p $HOME/bin && cp ./aws-iam-authenticator $HOME/bin/aws-iam-authenticator && export PATH=$PATH:$HOME/bin
      $ echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
      ```
##### kubectl
      ```
      $ sudo apt update
      $ curl -o kubectl https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/kubectl
      $ chmod +x ./kubectl
      $ mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin
      $ echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
      $ export KUBECONFIG=~/.kube/config
      ```
##### Tidy
      ```
      $ sudo apt install -y tidy
      ```

### Step 2: Create pipeline Cluster EKS
      - step 2.1: setting up AWS credentials within Jenkins
      - step 2.2: creating a pipeline based on repo (i.e. connect the repo to the Blue Ocean)
      - step 2.3: creating a cluster
      - step 2.4: setting up the k8s config 
### Step 3: Create pipeline Deployment Blue-Green
    - step 3.1: linting
    - step 3.2: building a Docker image
    - step 3.3: uploading the image to Dockerhub
    - step 3.4: setting the kubectl context
    - step 3.5: creating the Blue replica
    - step 3.6: creating the Green replica
    - step 3.7: changing routing
    - step 3.8: waiting for redirect the traffic to the green service
    - step 3.9: updating the service




 
##### TOOLS NEEDED FOR PIPELINES
 









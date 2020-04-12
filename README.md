# Udacity 
## Cloud DevOps Engineering Nanodegree
### Capstone project


The project includes:

* Working in AWS
* Using Jenkins to implement CI/CD
* Building pipelines
* Building Kubernetes clusters
* Building Docker containers in pipelines

### Stages
* Stage 1: Creating Cluster
    * step 1: setting up AWS credentials within Jenkins
    * step 2: creating a pipeline based on repo (i.e. connect the repo to the Blue Ocean)
    * step 3: creating a cluster
    * step 4: setting up the k8s config 
* Stage 2: Deployment
    * step 1: linting
    * step 2: building a Docker image
    * step 3: uploading the image to Dockerhub
    * step 4: setting the kubectl context
    * step 5: creating the Blue replica
    * step 6: creating the Green replica
    * step 7: changing routing
    * step 8: waiting for redirect the traffic to the green service
    * step 9: updating the service

#### Project Requirement:

* EC2
* Jenkins/ BlueOcean
* pip
* Docker
* kubectl
* awscli
* eksctl

#### Setup of EC2 for Jenkins

##### JDK
```
$ sudo apt update
$ sudo apt install default-jre            
$ sudo apt install openjdk-11-jre-headless
$ sudo apt install openjdk-8-jre-headless
```

##### Python
```
$ sudo apt update
$ sudo apt install python-pip
$ sudo apt install python3-pip
```

##### Nodejs
```
$ sudo apt update
$ sudo apt install nodejs
```

##### Ruby
```
$ sudo apt update
$ sudo apt install ruby-full
```

##### Docker
```
$ sudo apt update
$ sudo apt install apt-transport-https ca-certificates curl software-properties-common
$ curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
$ sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
```

##### awscli
```
$ pip3 install --upgrade --user awscli
$ sudo apt install awscli
$ aws configure
AWS Access Key ID [None]: XXXXXXXXXXXXXXXXXXXX
AWS Secret Access Key [None]: xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
Default region name [None]: us-east-1
Default output format [None]: json
```

##### VirtualBox
```
$ sudo apt update
$ wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- | sudo apt-key add -
$ wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -
$ sudo add-apt-repository "deb http://download.virtualbox.org/virtualbox/debian bionic contrib"
$ sudo apt install virtualbox-6.0
```

##### eksctl
```
sudo apt update
$ curl --silent --location "https://github.com/weaveworks/eksctl/releases/download/latest_release/eksctl_$(uname -s)_amd64.tar.gz" | tar xz -C /tmp
$ sudo mv /tmp/eksctl /usr/local/bin
```

##### aws-iam-authenticator
```
sudo apt update
$ curl -o aws-iam-authenticator https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/aws-iam-authenticator
$ chmod +x ./aws-iam-authenticator
$ mkdir -p $HOME/bin && cp ./aws-iam-authenticator $HOME/bin/aws-iam-authenticator && export PATH=$PATH:$HOME/bin
$ echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
```

##### minikube
```
$ sudo apt update
$ sudo apt install apt-transport-https
$ sudo apt upgrade
$ sudo apt install virtualbox virtualbox-ext-pack
$ wget https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64
$ chmod +x minikube-linux-amd64
$ sudo mv minikube-linux-amd64 /usr/local/bin/minikube
```

##### kubectl
```
sudo apt update
$ curl -o kubectl https://amazon-eks.s3-us-west-2.amazonaws.com/1.14.6/2019-08-22/bin/linux/amd64/kubectl
$ chmod +x ./kubectl
$ mkdir -p $HOME/bin && cp ./kubectl $HOME/bin/kubectl && export PATH=$PATH:$HOME/bin
$ echo 'export PATH=$PATH:$HOME/bin' >> ~/.bashrc
$ export KUBECONFIG=~/.kube/config
```

##### Jenkins
```
$ sudo apt update
$ wget -q -O - https://pkg.jenkins.io/debian/jenkins.io.key | sudo apt-key add -
$ sudo sh -c 'echo deb http://pkg.jenkins.io/debian-stable binary/ > /etc/apt/sources.list.d/jenkins.list'
$ sudo apt install jenkins
$ sudo usermod -a -G docker jenkins
$ sudo systemctl start jenkins
```

##### Tidy
```
sudo apt install -y tidy
```

#### Jenkins plugins
There are supposed to be installed plugins regarding Docker, k8s, BlueOcean, and AWS.





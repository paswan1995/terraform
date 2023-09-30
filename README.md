#### Terraform

###### DAY 1
* To preview README.md ctrl+shift+v
* 
## Problem Statement
* Our ficticious Organization:
    * name: Asquare info systems
    * Product: iEcommerce
    * Purpose: Any Organization can buy this project and host ecommerce  applications 
* This product is designed to work on any virtualized platform such as
    * VMWare
    * OpenStack
    * AWS
    * Azure
    * GCP
* Now Asquare info systems needs to have an apporach to deploy 
  the iEcommerce applicatio into Customers Cloud/Virtual Environments
* Architecture of iECommerce
![preview](images/Terraform1.jpg)

### Infra for iECommerce
* Two networks with connectivity b/w them 
  (same building, different    buildings, cities, countries)
* In Each network
* Two Databases
    * mysql
    * RAM: 8 GB
    * cpus: 2
    * Disk: 10 TB
  
    * one File Store
    * Size: 10 TB
  
    * 3 Servers:
    * OS: Ubuntu 22.04
    * RAM: 16 GB
    * Cpus: 2
    * Disk: 50 GB
* Solution:
* InfraProvisioning: This represents using Infrastructure as a Code
  and deploy to target environment
### Understanding InfraProvisioning
 * Analogy
  ![preview](images/Terraform2.jpg)
* We using InfraProvisioing tools where we express our desired state 
  about  infrastructure as code.
* Terraform: Can create infra in almost all the virtual environments
* ARM Templates: Can create infra in Azure
* Cloudformation: Can create infra in AWS
* Infraprovisiong tools use IaC which are generally idempotent
* Idempotance is the property which states execution one time
  or multiple times leads to the same result.
* Reusability is extreemely simple and terraform can also handle
  multiple environments (Developer, QA, UAT/Staging/Production).

  ###### DAY 2

* ### Terraform 
  
* Terraform is an opensource tool developed by HashiCorp which can 
  create infra in almost any virtual platform
* Terraform uses a language which is called as 
  `Hashicorp Configuration   Language (HCL)` to express desired State.

## Terms

* Resource: This is the infrastructure which you want to create
* Provider: This refers to where you want to create infrastructure
* The inputs which we express in teraform are called as `arguments`
* The output given by terraform is referred as `attribute`
  
  ## Installing terraform
 
* Refer Here @https://developer.hashicorp.com/terraform/downloads 
* we can install through command line also in windows 
  ````
  choco install terraform -y
  ````
* We have executed the commands in following order
  ![preview](images/Terraform3.jpg)
  ![preview](images/Terraform4.jpg)
  ![preview](images/Terraform5.jpg)
## Day--3

### N-Tier Application
* Consider the following architecture of a typical web application (ticket booking)
  ![preview](image.png)
* To realize this application on AWS, the high level overview is as shown below
  ![preview](image-1.png)
* To realize this application on Azure, the high level overview is as shown below
  ![preview](image-2.png)

### WOW (Ways of Working)
* Lets realize the architecture manually, make a note of
    * resource
    * inputs
    * outputs
* Find resources in Terraform to acheive the above manual steps

### Configuring a Provider in Terraform


* Create ec2 machine && ```sudo apt install unzip``` 
* Install Terraform on a linux machine
* Create a linux vm and ssh into it and execute the steps based on your distribution from here
* @https://developer.hashicorp.com/terraform/downloads
````
wget -O- https://apt.releases.hashicorp.com/gpg | sudo gpg --dearmor -o /usr/share/keyrings/hashicorp-archive-keyring.gpg
echo "deb [signed-by=/usr/share/keyrings/hashicorp-archive-keyring.gpg] https://apt.releases.hashicorp.com $(lsb_release -cs) main" | sudo tee /etc/apt/sources.list.d/hashicorp.list
sudo apt update && sudo apt install terraform
````
* create IAM user and generate access key and passwaord  
  ### AWS Provider
* Terraform aws provider uses the AWS APIs to get the infra created.
* To Create infrastructure in your AWS Account, it needs AWS programatic credentials 
  (Secret key and access key)
* To configure these keys @https://registry.terraform.io/providers/hashicorp/aws/latest/docs#authentication-and-configuration
* Create IAM Secret key and access key Refer Here for manual steps 
  @https://sst.dev/chapters/create-an-iam-user.html
  Lets write provider configuration
  ````
  provider "aws" {
    region = "ap-south-2"
    access_key = "AKIAZ4ECZC3PP5DPPHG6"
    secret_key = "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"
  }
``
* This is not a great way as we are having sensitive information in the text format.
* Best way is to install aws cli on the machine with terraform and terraform will automatically pickup
  credentials from there.
* Installing aws cli @https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
  ````
  sudo apt install unzip
  ````

``
  curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
``
* Now your provider can be as simple as 
````
provider "aws" {
    region = "us-west-2"
}
````

![preview](images/Terraform10.jpg)
![preview](images/Terraform11.jpg)
![preview](images/Terraform12.jpg)
![preview](images/Terraform13.jpg)
![preview](images/Terraform14.jpg)
![preview](images/Terraform15.jpg)
![preview](images/Terraform16.jpg)
![preview](images/Terraform17.jpg)
![preview](images/Terraform18.jpg)
![preview](images/Terraform19.jpg)
![preview](images/Terraform20.jpg)
![preview](images/Terraform21.jpg.png)
![preview](images/Terraform22.jpg.png.jpg)

###### DAY 4


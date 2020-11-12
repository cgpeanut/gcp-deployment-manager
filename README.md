# Infrastructure as Code - (iac) on GCP. 

Type of IT setup where developers and operatrions team automatically manage and provision the technology stack for an application
thru software rather than a manual process like configuring hardware or oepating systems.

## Chapter 1: intro to infrastructure as code (IAC) on GCP

creating infrstructure as code
```
```
* Understanding APIs
```
```
application programming interface, the main virtue of APIs is that they facilitate the relationship between two applciations to exchange messages or data.

3 ways to interact with the Google Cloud APIs
```
```
    01. GUI - Graphical User interface - Using the Google Cloud Console to provision resources.
```
```
    02. CLI - Command Line Interface - Tools and Libraries for interacting with Google Cloud products and services (gcloud)
```
```
    03. API - Application Programming Interface - Access Cloud APIs from server applications in a wide variety of popular programming languages.
```
```
The main virtue of APIs is that they facilitate the relationship between two applications to exchange messages or data. 
Messages or data are configuration files on GCP and when sent out to the deployment manager APIs will create a deploymentm, whether successfull or not the API will return a result. 
Which API are available in GCP, Which Tools we will use to connectto the APIs and Understand how to use GCP API to request IaaC. 
```
```
* Exploring Cloud Shell
Google Cloud SDK - gcloud deployment manager toolset to submit our order for resources on the google cloud platform.
Google Cloud Shell - cloud shell is a free adminmachine with browser-based command-line access for managing you 
infrastructure and applications on Google Cloud Platform. 
```
```
Iaac example - reserving and IP address, reitrering a DNs name with info blocks using the info blocks API
```
```
Five things to know about Google Cloud Shell.
```
    01. Cloud Shell: provides you with command-line access to your cloud resources directly from your browser./
```
```
    02. Built in Development Tools: You'll find Java, Go Python, Node.js, PHP and Ruby development tools.
```
```
    03. Cloud Editor: Cloud Shell comes with a built-in code editor that allows you to browse file directories as well as view and edit files. 
```
```
    04. Gcloud Command Line Tool: The gcloud CLI manages authentication, local configuration, developer workflow, interactions with Google Cloud APIs. 
```
```
    05. Google Cloud SDK: Tools and libraries for interacting with Google Cloud Products and services.
```
```



* Managing Version with Git
```
```
* Putting it all together
```
```

### Chapter 2 Depoloyment Manger 



* Ansible and Terraform installed on your machine.
* A registered OAuth application on Github.
* A pair of SSH keys.

### Terraform

First off, hop over to the Terraform directory.
```
cd terraform/
```
Run the `init.sh` script to initialize the required values.
```
chmod +x init.sh
./init.sh
```

Begin Terraforming!
```
terraform init
```
```
terraform plan
```
```
terraform apply
```
Store the ip address of the newly created compute instance in a variable, we will be using it shortly.
```
export VM_IP=$(terraform output ip)
```

### Ansible

Add the following line to Ansible's inventory, either `/etc/ansible/hosts` or a custom file. Be sure to pass in the newly minted IP address and your SSH private key.
```
droneci ansible_host=[IP] ansible_ssh_private_key_file=[SSH_PATH]
```

Switch over to the Ansible directory.
```
cd ansible/
```
Run the `init.sh` script to initialize the required values.
```
chmod +x init.sh
. ./init.sh
```
Check that Ansible can connect to your VM.
```
ansible droneci -m ping
```
Run the playbooks!
```
ansible-playbook playbooks/main.yaml
```





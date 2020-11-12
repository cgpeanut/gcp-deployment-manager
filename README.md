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
```
    GUI - Graphical User interface - Using the Google Cloud Console to provision resources.
```
```
```
    CLI - Command Line Interface - Tools and Libraries for interacting with Google Cloud products and services (gcloud)
```
```
```
    API - Application Programming Interface - Access Cloud APIs from server applications in a wide variety of popular programming languages.
```
```
```
* Exploring Cloud Shell
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





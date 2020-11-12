# Infrastructure as Code - (iac) on GCP. 

Type of IT setup where developers and operatrions team automatically manage and provision the technology stack for an application
thru software rather than a manual process like configuring hardware or oepating systems.

Chapter 1: intro to infrastructure as code (IAC) on GCP

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
# Managing Version with Git

[<img src="https://github.com/cgpeanut/gcp-deployment-manager/blob/main/data/git_flow.png">]

```
```
Concept of a command based repository - git, commit flow - why we add files to staging then to a repository, then push those files to a repository. 
Process of going thru multiple pass to see what works and having the ability to start over at the last point of progress. 
```
```
Adding Files to the  Repository
```
```
$ Git Add, Commit - Track chamges in the local repository
$ Git Clone - Create a local repository from a remote repository
$ Git Push, Pull - Retrieve more files from a remote repositiry, commit local files to a remote repository.

* Putting it all together
```
```
[<img src="https://github.com/cgpeanut/gcp-deployment-manager/blob/main/data/deployment-flow.png">]
```
```
Deployment Manager Features:
1. Parallel Deployment: Deploy many resources at one time, in parallel.
2. Updates: Add, delete, or change resources in the deployment.
3. Refenrences: One resource definition can reference another resource creating dependencies 
 and controlling the order of resource creation.
4. Templates: The Python and Jinja2 template that programmatically controls what gets deployed. 
5. Input & Output parameters: Pass variables (e.g.m zones machine sizem number of machines, state: test, prod,staging) into your templates and get ouput values back.
6. Preview Mode: See what changes the Deployemt Manager will make on a create or update operation before you commit the changes. 
```
```

### Chapter 2 Deployment Manager 
We use Google Deployment Manager to ctreate cloud resources with simple templates.
They all take an action and Feed
[<img src="https://github.com/cgpeanut/gcp-deployment-manager/blob/main/data/deployment-mgr-config-template-ex1.png">]
```
```
[<img src="https://github.com/cgpeanut/gcp-deployment-manager/blob/main/data/deployment-mgr-config-template-ex2.png">]
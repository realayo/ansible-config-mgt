# ansible-config-mgt

# Ansible Configuration Management - Automate Project 7 to 10

In Projects 7 to 10 you had to perform a lot of manual operations to set up virtual servers, install and configure required software, deploy your web application.


## Task

1. Install and configure Ansible client to act as a Jump Server/Bastion Host
2. Create a simple Ansible playbook to automate servers configuration

## Step 1 - Install and configure Ansible on EC2 Instance

1. We'll be using our Jenkins server from the previous project. 

1.  create a repo and name it ``ansible-config-mgt``
1. Instal Ansible
`sudo apt update`
`sudo apt install ansible`
1. check out ansible version by running `ansible --version`
![](https://user-images.githubusercontent.com/18899718/123687820-f965a380-d816-11eb-8983-6d9fe9806e31.png)

1. Configure Jenkins build job to save your repository content every time you change it 
- Create a new Freestyle project `ansible-mgt` in Jenkins and point it to your ‘ansible-config-mgt’ repository.
- Configure Webhook in GitHub and set webhook to trigger `ansible-mgt` build
- Configure a Post-build job to save all (**) files.

> Test your setup by making some change in master branch and make sure that builds starts automatically and Jenkins saves the files (build artifacts) in following folder 
`/var/lib/jenkins/jobs/ansible/builds/<build_number>/archive/`


![](https://user-images.githubusercontent.com/18899718/123694621-2a49d680-d81f-11eb-9349-1a2aff0832b9.png)


## Step 3 - Ansible Development
1. In `ansible-config-mgt` GitHub repository, create a new branch that will be used for development of a new feature. Our branch will be named `feature/prj-11-ansible`
1. Checkout the newly created feature branch `feature/prj-11-ansible` to your local machine and start building your code and directory structure.
`git checkout -b feature/prj-11-ansible`
1. Create a directory and name it playbooks
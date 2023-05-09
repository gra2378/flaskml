# flaskml
This is a repo for Flask Machine Learning Predictions


# Overview

<TODO: complete this with an overview of your project>

## Project Plan
<TODO: Project Plan

* A link to a Trello board for the project

https://trello.com/b/TC2KuexL/ci-cd-pipeline


* A link to a spreadsheet that includes the original and final project plan>



## Instructions

<TODO:  
* Architectural Diagram (Shows how key parts of the system work)>

<TODO:  Instructions for running the Python project.  How could a user with no context run this project without asking you for any help.  Include screenshots with explicit steps to create that work. Be sure to at least include the following screenshots:

* Project running on Azure App Service

## Create Repo in Github

## Create SSH keys to allow encrypted communication between GitHub and Azure CLI

ssh-keygen -t rsa
enter, enter, enter

![image](https://github.com/gra2378/flaskml/assets/133028180/afb8a4a4-8a97-4ed0-8008-60c7125333df)


cat /home/odl_user/.ssh/id_rsa.pub 


## Clone Project into Azure Cloud Shell

In Azure CLI in a folder of your choosing 
git clone git@github.........

Are you sure you want to continue connecting?  yes

## Set up virtual environment

Navigate into the folder inside of the github repo and type the following commands

python3 -m venv ~/.(name of repo)
  
source ~/.(name of repo)/bin/activate
  
## Run Make Install
  
run 
make install
  
Output will look something  like this:
  
  ![image](https://user-images.githubusercontent.com/120996688/236907997-c3b5c2b7-6e47-4036-8004-25903ce5fc22.png)

##Create the app service, deploy app, and verify that it has been deployed
  az webapp up -n <your-appservice>
  for example mine was:
  az webapp up -n flask-ml-serv-d
  
  Go to https://(your appservice).azurewebsites.net/
  
  It will look something like this:
  
  ![image](https://user-images.githubusercontent.com/120996688/236912797-0ef0dd37-a3b9-4e4e-8c6c-ca61cc3aae01.png)

  ##Perform a prediction
  
  In your GitHub Repo, go to make_predict_azure_app.sh.  Change the following line to the name of your app:
  
  -X POST https://(your app service).azurewebsites.net:$PORT/predict
  
  Go back to Azure CLI and run the following to update the changes.
  
  git fetch 
  
  New Azure service connection
  ![image](https://user-images.githubusercontent.com/120996688/236942382-08985d50-fc17-4b31-828a-6bfcb7169e91.png)

  
  
* Passing tests that are displayed after running the `make all` command from the `Makefile`

* Output of a test run

* Successful deploy of the project in Azure Pipelines.  [Note the official documentation should be referred to and double checked as you setup CI/CD](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).

* Running Azure App Service from Azure Pipelines automatic deployment

* Successful prediction from deployed flask app in Azure Cloud Shell.  [Use this file as a template for the deployed prediction](https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code/blob/master/C2-AgileDevelopmentwithAzure/project/starter_files/flask-sklearn/make_predict_azure_app.sh).
The output should look similar to this:

```bash
udacity@Azure:~$ ./make_predict_azure_app.sh
Port: 443
{"prediction":[20.35373177134412]}
```

* Output of streamed log files from deployed application

> 

## Enhancements

<TODO: A short description of how to improve the project in the future>

## Demo 

<TODO: Add link Screencast on YouTube>


# flaskml
This is a repo for Flask Machine Learning Predictions

This document will walk you throw how to make a prediction






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
![image](https://github.com/gra2378/flaskml/assets/133028180/87344aa2-a98e-4aa0-b8f4-8739eb29e7d2)



## Clone Project into Azure Cloud Shell

Go to your repo in Gitbhub and copy the Clone with SSH Key
![image](https://github.com/gra2378/flaskml/assets/133028180/de8ff4ea-e108-4977-a399-337787d58c25)


In Azure CLI in a folder of your choosing 
git clone git@github.com:gra2378/flaskml.git

![image](https://github.com/gra2378/flaskml/assets/133028180/008ebb05-035f-4203-b2a3-2d033e868065)

Are you sure you want to continue connecting?  yes

test a change within Azure CLI:

![image](https://github.com/gra2378/flaskml/assets/133028180/21394360-faab-40e2-8409-dbf883a135ff)

![image](https://github.com/gra2378/flaskml/assets/133028180/3adc0ab5-dc26-484f-9a67-48ce8e4eaa26)
![image](https://github.com/gra2378/flaskml/assets/133028180/133fa96b-f16c-429e-8aef-f50c2f0f69fd)

Retrieving changes made in github and refreshing Azure CLI:

git pull

![image](https://github.com/gra2378/flaskml/assets/133028180/8064a281-75a0-4c41-b02f-beeb60ffa217)


## Set up virtual environment

Navigate into the folder inside of the github repo and type the following commands

python3 -m venv ~/.(name of repo)
  
source ~/.(name of repo)/bin/activate

![image](https://github.com/gra2378/flaskml/assets/133028180/03f0d17d-ce6c-4eaa-a5e8-3b148f59bb97)

  
## Run Make Install
  
run 
make install
  
Output will look something  like this:
  
![image](https://github.com/gra2378/flaskml/assets/133028180/44df0509-81c5-4ddb-8611-0ef1d1b5a4d8)
![image](https://github.com/gra2378/flaskml/assets/133028180/65f2d1d9-91e1-430b-a95e-be7bc1b2792e)

## GitHub Actions

Enable GitHub Acctins and Create yml file

![image](https://github.com/gra2378/flaskml/assets/133028180/dd30a221-afa9-40ac-855d-94483286f7f6)

Verify that tests passed:

![image](https://github.com/gra2378/flaskml/assets/133028180/f89d8cc3-c128-4913-857b-94c8d9b41551)

## Create the app service, deploy app, and verify that it has been deployed
  az webapp up -n (your-appservice)
  
  For example mine was, but I added a resource group.
  
  az webapp up -n flask-ml-serv-d
  
  ![image](https://github.com/gra2378/flaskml/assets/133028180/07edff04-b1b2-46fd-a43f-d57de97c0785)

  
  Go to https://(your appservice).azurewebsites.net/
  
  It will look something like this:
  
  ![image](https://github.com/gra2378/flaskml/assets/133028180/12021a6f-f73b-4cf1-9b5c-fe3f165376c3)


  ## Perform a prediction
  
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



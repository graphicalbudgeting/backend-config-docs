# Set up the Graphical Budgeting Backend
## OverView
This document describes how to set up MongoDB Cloud as a backend for Graphical Budgeting.

Your understanding of MongoDB Realm and Atlas will help you in the following steps.

https://docs.mongodb.com/realm/

https://docs.atlas.mongodb.com


To use MongoDB Cloud, you'll need a MongoDB Atlas account first.
Then, create a cluster in MongoDB Atlas and a Realm App that links to the cluster.

Your Realm App for Graphical Budgeting should be created and updated using the Realm App Configuration provided by Graphical Budgeting.

As the deployment method, you can choose Automatic GitHub Deployment or Realm CLI.
This document explains how to deploy with GitHub.

https://docs.mongodb.com/realm/deploy/deploy-automatically-with-github/

In this document, git operations are described assuming the use of GitHub Desktop.


The general flow is the same as in the Set up the Task Tracker Tutorial Backend, so please refer to the following links as well.

https://docs.mongodb.com/realm/tutorial/realm-app/

## 1. Create an atlas account
Create your Atlas Account. After logging in, create an Atlas Organization and then create a Project.

https://docs.atlas.mongodb.com/tutorial/create-atlas-account/

## 2. Create an atlas Cluster

Create your Atlas Cluster for your Graphical Budgeting Realm App.

https://docs.atlas.mongodb.com/tutorial/deploy-free-tier-cluster/

https://docs.atlas.mongodb.com/tutorial/create-new-cluster/

### Note
Do not select the serverless instance for database deployment type, as it is a preview release and has not been tested in Graphical Budgeting.

## 3. Create a GitHub Repository

Create a GitHub account first.

https://github.com

Create your GitHub Repository for your Graphical Budgeting Realm App.

https://docs.github.com/en/get-started/quickstart/create-a-repo

### Note
You must check “Initialize this repository with a README”. Otherwise, the branch will not be created and you will not be able to complete the GitHub Setting at the App Deployment.

https://docs.github.com/en/github/collaborating-with-pull-requests/proposing-changes-to-your-work-with-pull-requests/creating-and-deleting-branches-within-your-repository


## 4. Create a Realm App

Realm App can be created by MongoDB Atlas UI.

https://docs.mongodb.com/realm/get-started/create-realm-app/

### Note
You can set up the GitHub to connect to when you create a Realm App, do not set it up now.
We will be setting it up in the next step.


## 5. Set up automatic deployment with GitHub

Configure automatic deployment with GitHub for your Realm app you just created.

https://docs.mongodb.com/realm/deploy/deploy-automatically-with-github/

### Note
Perform only steps 1, 2 and 4.

## 6. Export your Realm App Configuration

Realm App Configuration is provided by Graphical Budgeting, but realm_config.json should be replaced with the one of your environment. Export your Realm App Configuration to get that.

https://docs.mongodb.com/realm/deploy/export-realm-app/

## 7. Install GitHub Desktop on your client and Authenticate to GitHub

7-1. Install GitHub Desktop on your client.

https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/installing-and-authenticating-to-github-desktop/installing-github-desktop

7-2. Authenticating an account on GitHub.

https://docs.github.com/en/desktop/installing-and-configuring-github-desktop/installing-and-authenticating-to-github-desktop/authenticating-to-github

## 8. Setting up GitHub Desktop

8-1. Clone your repository.

https://docs.github.com/en/desktop/contributing-and-collaborating-using-github-desktop/adding-and-cloning-repositories/cloning-and-forking-repositories-from-github-desktop#cloning-a-repository

### Note
It’s a good idea to set the Local Path so that the last directory name is the same as the repository name.

/…/your GitHub Repository Name


8-2. Set the following files types to Ignored Files.

Repository > Repository Settings > Ignored Files

.DS_Store
.gitattributes
.gitignore

## 9. Download Application Configuration For Graphical Budgeting

Of course, you can run the git clone command or use GitHub Desktop, we'll simply download it from GitHub to avoid confusion.

Access to the Graphical Budgeting Repository on the GitHub, select the Code tab and click the Code button. Then you can see Download Zip and click it.

https://github.com/graphicalbudgeting/backend-config


## 10. Extract the downloaded zip file and Override realm_config.json

Extract the downloaded zip file and place them under the directory set as Local Path when cloning your repository. Then, replace the realm_config.json in the root directory with your realm_config.json.

### Note
The name of the root directory of the extracted file must match the directory name you set at Deployment in the left navigation menu of the Realm UI, Configuration tab, 2 Select your GitHub Repository, Directory.

The name of the root directory of the file that Graphical Budgeting provide is <backend-config>, so if you set a different name from this, be sure to change it to the name you set in the Deployment.

## 11. Commit changes and push them to GitHub

11-1. You can see the changes in the GitHUB Desktop. Write your commit message and commit your changes to main.

11-2. Click Push origin to push your local changes to the remote repository.

## 12. Verify that the Graphical Budgeting Backend is Properly Configured

Click Deployment in the left navigation menu of the Realm UI and select the History tab, then you can see the deployment history. Check the latest deployment status.


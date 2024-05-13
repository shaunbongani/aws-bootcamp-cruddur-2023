# Week 0 — Billing and Architecture

# Getting the AWS CLI Working
Proceeding to install the account

# Install AWS CLI
 -We install our AWS CLI when the Gitpod environment launches

 -We are going to set AWS CLI to use partial aoutoprompt mode to make it easier to debug CLI commands.

 -The bash commands we are using are the same as the [AWS CLI install instruction]https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html

## Update our .gitpod.yml to include the following task.
 
  tasks:
  - name: aws-cli
    env:
      AWS_CLI_AUTO_PROMPT: on-partial
    init: |
       cd /workspace
       curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
       unzip awscliv2.zip
       sudo ./aws/install
       cd $THIA_WORKSPACE_ROOT
vscode:
  extensions:
    - 42Crunch.vscode-openapi


# Create a new User an d Generate AWS Credentials

 -Go to IAM User Console

 -Enable console access

 -Create a new Admin Group and apply administratorAccess

 -Create the user and go find and click into the user

 -Choose AWS CLI Access

 -Download the CSV with the credentials 


 # Set Env Var

  -export AWS_ACCESS_KEY_ID=""

  -export AWS_SECRET_ACCESS_KEY=""

  -export AWS_DEFAULT_REGION=us-Central-1


# We'll tell Gitpod to remember these credentials if we relaunch our workspaces

  -gp env AWS_ACCESS_KEY_ID=""

  -gp env AWS_SECRET_ACCESS_KEY=""
  
  -gp env AWS_DEFAULT_REGION=us-Central-1

# Check that the AWS CLI is working and you are the expected user

aws sts get-caller-identity

You should see something like this 
# Integrating a GitHub Repository with AWS

**Difficulty:** Easy-ish  
**Time:** 60 min  

## What You’ll Need:
- **An AWS account** – [Create one here!](https://aws.amazon.com/)
- **Part 1 of this series** – VSCode (if not already done)

## AWS Services:
- **Amazon EC2**
- **VSCode**
- **GitHub**

---

### ⚡️ 30-second Summary

Welcome to your DevOps x AWS project series! 

In this SEVEN-project series, you will create a CI/CD pipeline to build and deploy a simple web application using AWS' Code services. 

Here's what you'll build at the end of ALL seven projects ⬇️ 

![Workflow](https://learn.nextwork.org/projects/static/aws-devops-vscode/architecture-complete.png "Workflow showing the CI/CD pipeline architecture involving AWS services")  
<p align="center">Yup, you'll build all of this from scratch, and we'll do every step together.</p>  

Welcome to Project 2 of your DevOps x AWS project series! In this project, you’ll learn how to store your web application's source code in a GitHub repository and integrate it with AWS.

If you haven’t done Project 1 yet, we recommend completing it first. But no worries if you’re new to repositories; you’ll learn all the essentials in this project!

### What You’ll Build:
At the end of this project, you'll have:
- Set up Git and GitHub
- Connected your web app project to a GitHub repo
- Updated your web app files and pushed them to your GitHub repo
![You'll be setting up a repository for your source code!](https://learn.nextwork.org/projects/static/aws-devops-github/architecture-today.png)  
<p align="center">You'll be setting up a repository for your source code!</p>  

---

### 💂‍♀️ Step 1: **Set Up an IAM User**

1. Log in to your AWS account with your IAM user.

---

### 🧱 Step 2: **Set Up Your Web App in the Cloud** (Project 1 of this DevOps Series)

We recommend completing Project 1 of this DevOps series first before proceeding. If you've already completed it, head straight to Step #3: Install Git.

---

### ⬇️ Step 3: **Install Git**

Now that your development environment is ready, let's install Git on your EC2 instance.

1. Open your EC2 instance’s terminal.
2. Run these commands to install Git:

```bash
# Update the package list
sudo dnf update -y

# Install Git
sudo dnf install git -y

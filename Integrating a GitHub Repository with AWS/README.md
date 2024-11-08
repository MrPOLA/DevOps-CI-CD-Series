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

<p align="center">💂‍♀️ Step 1: Set Up an IAM User </p> 

1. Log in to your AWS account with your IAM user.

---

<p align="center"> 🧱 Step 2: Set Up Your Web App in the Cloud (Project 1 of this DevOps Series) </p

We recommend completing Project 1 of this DevOps series first before proceeding. If you've already completed it, head straight to Step #3: Install Git.

---

<p align="center">⬇️ Step 3: Install Git</p>

Now that your development environment is ready, let's install Git on your EC2 instance.

1. Open your EC2 instance’s terminal.
2. Run these commands to install Git:

```bash
# Update the package list
sudo dnf update -y

# Install Git
sudo dnf install git -y
```

![Install Git](https://learn.nextwork.org/projects/static/aws-devops-github/3.1.png)
<p align="center">Install Git.</p>  

3. Verifiy the installation:
   
```bash
git --version
```

![Run a git version check](https://learn.nextwork.org/projects/static/aws-devops-github/3.2.png)
<p align="center">Run a git version check.</p>  

---

<p align="center">🔌 Step #4</p>

Git is installed, woohoo! Next up, we'll set you up with GitHub.

In this step, you're going to:

1. **Set up a GitHub account** (if you don't have one).
2. **Create a GitHub repository**.

---

If you already have a GitHub account:
- Sign in to GitHub.
- Scroll to the heading 🗂️ **Set up a new repository** below.

If you don't have a GitHub account, no worries! Signing up is free and takes just 5 minutes.  
Head to GitHub's [signup page](https://github.com/join).

---

💡 **What is the difference between Git & GitHub?**  
If Git is the tool for tracking changes, think of GitHub as a storage space for different versions of your project that Git tracks. Since GitHub is a cloud service, it also lets you access your work from anywhere and collaborate with other developers over the internet.

💡 **Why would I use GitHub? Isn’t the code in my EC2 instance already in the cloud?**  
Even though your code is on a cloud server like EC2, GitHub helps you use Git and see your file changes in a more user-friendly way. It's just like how using an IDE (VSCode) makes editing code easy.  

GitHub is especially useful when you're working in teams and need to share your updates and reviews with others on a shared codebase.

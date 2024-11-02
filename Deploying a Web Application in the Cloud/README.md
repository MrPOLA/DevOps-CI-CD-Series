# Deploying a Web Application in the Cloud

## Kick off your DevOps CI/CD series with this foundational project!

**DIFFICULTY💪** - Easy-ish  
**TIME⌚** - 120 mins  

**WHAT YOU'LL NEED 📝**  
- An AWS account - [Create one here!](https://signin.aws.amazon.com/signup?request_type=register)  
- **AWS SERVICES**  
    1. Amazon EC2  
    2. VSCode  

⚡️ **30 second Summary.**

Welcome to your DevOps x AWS project series! 

In this SEVEN-project series, you will create a CI/CD pipeline to build and deploy a simple web application using AWS' Code services. 

Here's what you'll build at the end of ALL seven projects ⬇️ 

![Workflow](https://learn.nextwork.org/projects/static/aws-devops-vscode/architecture-complete.png "Workflow showing the CI/CD pipeline architecture involving AWS services")  
<p align="center">Yup, you'll build all of this from scratch, and we'll do every step together.</p>  

&nbsp;

🧠 **What's CI/CD? Why do this project?**  

Engineers are often working in big teams and collaborating on complex software projects. Managing the many, MANY changes in a project can get messy without the right processes in place. A CI/CD (Continuous Integration and Continuous Deployment/Delivery) pipeline is a key tool to automate the steps from development (i.e. created by developers) to deployment (i.e. published to users), which helps software get built and released even faster. 

In the first project of this series, you'll learn the basics of building a web app using AWS and another tool called VSCode. This will lay the foundation for your DevOps work for the rest of this series! 

Get ready to:  
- 💻 Launch an EC2 instance.  
- 🔌 Use VSCode to set up a remote SSH connection to your EC2 instance.  
- ☕️ Install Maven and Java and generate a basic web app.

## Your Step-By-Step Guide

<p align="center">💂‍♀️ Step #1</p> 

**Set up an IAM user**  

Before we dive in, log in to your AWS account with your IAM user.  

![What you're building in this step.](https://learn.nextwork.org/projects/static/aws-devops-vscode/1.0-framed.png)  
<p align="center">What you're building in this step.</p>  

&nbsp;

- Log In with your IAM Admin User.
- If you've logged in successfully as your IAM User, skip to the next step.
If you don't have an IAM user yet - here are the steps to create one (this takes less than 10 mins).  

💡 **What is an IAM user? Why are we setting one up?**  
In AWS, a user is a person or a computer that can do things on the AWS cloud. When you create an AWS account for the first time, the login you get is called the root user of the AWS account. AWS actually recommends to not use your root user for everyday tasks to protect it from security breaches. You should create IAM users instead. If a root user is a master key to your AWS account, think of IAM users as key copies. IAM users have separate usernames and passwords to your root user, and you can set them to have limited access to your account's resources.

Here’s how to create an IAM user:  
- Head to your AWS Account as the root user.  
- Open the AWS IAM console.  
- From the left-hand navigation panel, choose Users.  
- Choose Create user.  
- For the User name, use `Yourname-IAM-Admin`. Make sure to select the checkbox next to Provide user access to the AWS Management Console - optional. This does not apply to all accounts, but if you're prompted with a pop-up panel that says Are you providing access to a person?, choose I want to create an IAM user.  

![If this panel pops up select 'I want to create an IAM user'](https://learn.nextwork.org/projects/static/aws-security-iam/high-step4.4.png)  
<p align="center">If this panel pops up select 'I want to create an IAM user'</p>  

&nbsp;

- For the console password, choose Custom password. Type in a password that you will be able to remember/access in the future.  
- Deselect the checkbox for Users must create a new password at next sign-in - Recommended.  

![Creating your user.](https://learn.nextwork.org/projects/static/aws-security-iam/high-step4.3.png)  
<p align="center">Creating your user.</p>  

&nbsp;

- Choose Next. In the permissions setup page, choose Attach policies directly.  
- From the list of Permissions policies, select AdministratorAccess.  
- Choose Next. Choose Create user. Voilà - you've just created your new user! Stay on this page.  
- Choose Download .csv file. Copy the Console sign-in URL. Now you're ready to start using your IAM user. 🏁
- Log out of your root user's AWS Account.
- Paste and go to your copied console sign-in URL.
- Open your downloaded .csv file containing your user's access instructions.  
🙏 **PLEASE make sure you log in to your IAM Admin User instead of the root user - it's truly best practice for account security.**

---

☁️ **Step #2**  
**Launch an EC2 Instance**  

Before we get into the juicy work of building your web app, we need to set up a home for your web app's files. Since we want your web app to be entirely created and run on the cloud, we'll use a virtual server (EC2 instance) to house our development work.  

Let's get an EC2 instance up and running!  

In this step, you're going to:  
- Launch a new EC2 instance.  
- Set up a key pair for secure access.  
- Set up network settings for your instance.

![What you're building in this step.](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.0-framed.png)  
<p align="center">What you're building in this step.</p>  

&nbsp;

- Head to Amazon EC2 in your AWS Management Console.  

![Head to EC2](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.1.png)  
<p align="center">Head to EC2</p>  

&nbsp;

Switch your Region to the one closest to you.  
<p align="center">Switch your region to one closest to you.</p>  

&nbsp;

- In your EC2 console, select Instances from the left-hand navigation panel. Choose Launch instances.  

![Select Launch instances.](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.3.png)  
<p align="center">Select Launch instances.</p>  

&nbsp;

- Let's set up your EC2 instance.
- In Name, enter the value `nextwork-devops-yourname`.
  -  Don't forget to replace yourname with your name!
- Choose Amazon Linux 2023 AMI under Amazon Machine Image (AMI).  

![Select Amazon Linux 2023 AMI](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.4.png)  
<p align="center">Select Amazon Linux 2023 AMI</p>  

&nbsp;

- Leave t2.micro under Instance type.
- Under Key pair (login), choose Create a new key pair.  

![Create a new key pair.](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.5.png)  
<p align="center">Create a new key pair.</p>  

&nbsp;

- Use `nextwork-keypair` as your key pair's name.
- Keep the Key pair type as RSA, and the Private key file format as .pem.
- Select Create key pair.  

![Set up your new key pair.](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.6.png)  
<p align="center">Set up your new key pair.</p>  

&nbsp;

- A new file will automatically download to your local computer - nice! This is your private key.
- Before we lose track of our .pem file, let's organize it on our computer.
- Head to your local computer's desktop.
- Create a new folder on your desktop called `DevOps`.
- Move your .pem file from your Downloads folder into your DevOps folder.
- Back to our EC2 instance setup, head to the Network settings section.
- For Allow SSH traffic from, select the dropdown and choose My IP. This ensures that only you can access your EC2 instance.
- Double-check that the IP address under My IP is correct - you can check your IP by clicking here.
- If your IP address is different from what's under My IP, select Custom from the dropdown instead. Enter your IP and make sure to add a /32 to the end e.g. `012.345.678.9/32`.
- Leave the default values for the remaining sections.  

![Your EC2 instance's Networking settings.](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.9.png)  
<p align="center">Your EC2 instance's Networking settings.</p>  

&nbsp;

- When you're ready, choose Launch instance.
- Success 😎  

![Success!](https://learn.nextwork.org/projects/static/aws-devops-vscode/2.11.png)  
<p align="center">Success!</p>  

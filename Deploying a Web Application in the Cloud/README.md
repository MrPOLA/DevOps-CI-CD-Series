# Deploying a Web Application in the Cloud ☁️

## Kick off your DevOps CI/CD series with this foundational project! 🚀

**DIFFICULTY 💪** - Easy-ish  
**TIME ⌚** - 120 mins  

**WHAT YOU'LL NEED 📝** - An AWS account - [Create one here!](https://signin.aws.amazon.com/signup?request_type=register)  
**AWS SERVICES** - 
1. [Amazon EC2](https://aws.amazon.com/ec2/) 🖥️
2. VSCode 💻

⚡️ **30 Second Summary**: Welcome to your DevOps x AWS project series! In this SEVEN-project series, you will create a CI/CD pipeline to build and deploy a simple web application using AWS' Code services. Here's what you'll build at the end of ALL seven projects ⬇️.

![Workflow](https://learn.nextwork.org/projects/static/aws-devops-vscode/architecture-complete.png "Workflow showing the CI/CD pipeline architecture involving AWS services")
<div align="center">Yup, you'll build all of this from scratch, and we'll do every step together.</div>


🧠 **What's CI/CD? Why do this project?** Engineers are often working in big teams and collaborating on complex software projects. Managing the many, MANY changes in a project can get messy without the right processes in place. A CI/CD (Continuous Integration and Continuous Deployment/Delivery) pipeline is a key tool to automate the steps from development (i.e., created by developers) to deployment (i.e., published to users), which helps software get built and released even faster. 

In the first project of this series, you'll learn the basics of building a web app using AWS and another tool called VSCode. This will lay the foundation for your DevOps work for the rest of this series. Get ready to:

💻 Launch an EC2 instance.  
🔌 Use VSCode to set up a remote SSH connection to your EC2 instance.  
☕️ Install Maven and Java and generate a basic web app.  

If you would like guidance on any particular project stage, such as setting up CodeBuild or configuring CodePipeline, feel free to reach out! 🙌

## Your Step-By-Step Guide 💂‍♀️

### Step #1: Set Up an IAM User

Before we dive in, log in to your AWS account with your IAM user. 

![What you're building in this step.](https://learn.nextwork.org/projects/static/aws-devops-vscode/1.0-framed.png)  
<div align="center">What you're building in this step.</div>

#### Log In with your IAM Admin User
- If you've logged in successfully as your IAM User, skip to the next step.
- If you don't have an IAM user yet, here are the steps to create one (this takes less than 10 mins).

💡 **What is an IAM user? Why are we setting one up?**  
In AWS, a user is a person or a computer that can do things on the AWS cloud. When you create an AWS account for the first time, the login you get is called the root user of the AWS account. AWS recommends not using your root user for everyday tasks to protect it from security breaches. 

You should create IAM users instead. If a root user is a master key to your AWS account, think of IAM users as key copies. IAM users have separate usernames and passwords from your root user, and you can set them to have limited access to your account's resources.

#### Follow these steps to create an IAM user:
1. Head to your AWS Account as the root user.
2. Open the AWS IAM console.
3. From the left-hand navigation panel, choose **Users**.
4. Choose **Create user**.
5. For the User name, use `Yourname-IAM-Admin`.
6. Make sure to select the checkbox next to **Provide user access to the AWS Management Console - optional**. If prompted with a pop-up panel that says **Are you providing access to a person?**, choose **I want to create an IAM user**.

   ![If this panel pops up, select 'I want to create an IAM user'](https://learn.nextwork.org/projects/static/aws-security-iam/high-step4.4.png)  
   <div align="center">If this panel pops up, select 'I want to create an IAM user'.</div>

7. For the console password, choose **Custom password**. Type in a password that you will remember.
8. Deselect the checkbox for **Users must create a new password at next sign-in - Recommended**.

   ![Creating your user.](https://learn.nextwork.org/projects/static/aws-security-iam/high-step4.3.png)  
   <div align="center">Creating your user.</div>

9. Choose **Next**. 
10. In the permissions setup page, choose **Attach policies directly**. From the list of Permissions policies, select **AdministratorAccess**.
11. Choose **Next**.
12. Choose **Create user**. Voilà - you've just created your new user! Stay on this page.
13. Choose **Download .csv file**. 
14. Copy the Console sign-in URL.

Now you're ready to start using your IAM user! 🏁

- Log out of your root user's AWS Account.
- Paste and go to your copied console sign-in URL.
- Open your downloaded .csv file containing your user's access instructions.
- Log in using your IAM user's username and password from the .csv file.

🙏 **PLEASE make sure you log in to your IAM Admin User instead of the root user - it's truly best practice for account security.**

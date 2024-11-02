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

### Project Overview 🌟
In this project series, you'll leverage various AWS services to automate the deployment of a web application. The architecture depicted in the image above outlines the key components involved:

- **GitHub**: Your source code repository where you will store your application code. 📦
  
- **AWS CodeArtifact**: A fully managed artifact repository service to store and share your build artifacts. 🗃️

- **AWS CodeBuild**: This service will compile your source code, run tests, and produce software packages that are ready to deploy. It allows you to automate the building process. 🛠️

- **AWS CodePipeline**: A continuous integration and continuous delivery (CI/CD) service that automates the build, test, and release process. It integrates with other AWS services to provide a seamless workflow. 🔄

- **AWS CodeDeploy**: This service automates the deployment of applications to Amazon EC2 instances, ensuring that your application is up-to-date with the latest changes. 📈

- **AWS CloudFormation**: A service that helps you model and set up your AWS resources so that you can spend less time managing those resources and more time focusing on your applications. 🏗️

- **Amazon S3**: Used for storing your build artifacts and any static assets needed for your web application. 🗄️

### Workflow Breakdown 🔍
1. **Source Code Management**: Your journey begins in GitHub, where the application code is maintained and versioned. 🌐

2. **Automated Build Process**: With AWS CodeBuild, your code will be compiled and tested automatically upon each commit. This ensures that you are always working with a stable version of your application. 🔨

3. **Artifact Storage**: The build artifacts generated during the build process are stored in AWS CodeArtifact for easy access and management. 📂

4. **Continuous Delivery Pipeline**: AWS CodePipeline orchestrates the entire workflow from code commit to deployment. It triggers builds, runs tests, and prepares the application for deployment. 📈

5. **Deployment to EC2**: AWS CodeDeploy automates the deployment of your application to EC2 instances within your VPC, making it easily scalable and manageable. 🌍

6. **Infrastructure as Code**: With AWS CloudFormation, you can manage your infrastructure through code, enabling you to deploy and manage your resources in a repeatable and predictable manner. 📜

Breaking this setup down into a seven-project series will allow you to focus on each component individually, ensuring a solid understanding of each service and its role in the overall architecture.

If you would like guidance on any particular project stage, such as setting up CodeBuild or configuring CodePipeline, feel free to reach out! 🙌

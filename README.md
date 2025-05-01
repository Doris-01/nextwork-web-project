# 🚀 Nextwork DevOps Challenge Project

This repository showcases a complete DevOps CI/CD pipeline using AWS services. The project walks through the process of building, packaging, and deploying a Maven-based web application using CodeArtifact, CodeBuild, CodeDeploy, and CodePipeline.

---

## 📌 Project Overview

The objective of this project is to deploy a Maven web application using a fully automated DevOps pipeline on AWS.

---

## 🔧 Tools Installed on EC2 Instance

- **Maven**
- **Java (Amazon Corretto 8)**
- **Git**
- **VS Code (Remote SSH)**

---

## 🔨 Challenge Steps and Implementation

### 1️⃣ Set Up a Web App in the Cloud
- Launched an EC2 instance on AWS with Java, Maven, and Git installed.
- Configured VS Code to connect via Remote SSH for local development in the cloud.

### 2️⃣ Create a CodeArtifact Repository
- Created an AWS CodeArtifact repository to store Maven dependencies.
- Configured `settings.xml` to authenticate Maven with CodeArtifact.

### 3️⃣ Set Up IAM Access for CodeArtifact
- Created an IAM policy for CodeArtifact access.
- Attached the policy to a role assumed by the EC2 instance via its instance profile.

### 4️⃣ Connect CodeArtifact to Maven
- Ran authentication command using `aws codeartifact login` for Maven.
- Verified Maven was able to fetch and upload artifacts to CodeArtifact.

### 5️⃣ Store Build Artifacts in S3
- Launched an S3 bucket to store `.zip` files or `.jar` build outputs from CodeBuild.

### 6️⃣ Launch CloudFormation Stack for Deployment
- Used AWS CloudFormation to spin up the deployment EC2 instance with the correct IAM role, tags, and instance profile.

### 7️⃣ Set Up CodeDeploy
- Created a CodeDeploy application and deployment group.
- Wrote `appspec.yml` and custom lifecycle scripts to manage deployments.

### 8️⃣ Configure CodeDeploy IAM Service Role
- Created a role for CodeDeploy with policies for EC2 and S3 access.

### ✅ Successfully Deploy the Web App
- Triggered a manual deployment via CodeDeploy to test infrastructure and deployment lifecycle scripts.

### 9️⃣ Set Up a CodeBuild Project
- Created a `buildspec.yml` in the repo defining Maven build steps.
- Configured a CodeBuild project to pull code from GitHub, run Maven build, and upload artifacts to S3.

### 🔑 Update CodeBuild IAM Role
- Attached policies allowing CodeBuild to:
  - Access CodeArtifact
  - Fetch dependencies
  - Push artifacts to S3

### 🔁 Set Up CodePipeline (CI/CD)

- **Source Stage**: Connected CodePipeline to GitHub using a personal access token.
- **Build Stage**: Connected to CodeBuild project.
- **Deploy Stage**: Connected to CodeDeploy deployment group.

### 🔔 Automate Trigger with Webhooks
- Configured webhook in GitHub to trigger CodePipeline on `push` events.

---

## 🗂️ File Structure
. ├── appspec.yml ├── buildspec.yml ├── scripts/ │ ├── install_dependencies.sh │ ├── start_server.sh │ └── stop_server.sh ├── src/ │ └── Main.java / HTML / App Files └── README.md


---

## 🧪 Final Test
- Committed and pushed code to GitHub.
- Verified CodePipeline:
  - Pulled source
  - Built with Maven via CodeBuild
  - Stored artifact in S3
  - Deployed to EC2 using CodeDeploy
- Rollback policies tested for disaster recovery.

---

## 🧰 AWS Services Used

- **Amazon EC2**
- **Amazon S3**
- **AWS CodeArtifact**
- **AWS CodeBuild**
- **AWS CodeDeploy**
- **AWS CodePipeline**
- **AWS IAM**
- **AWS CloudFormation**

---

## 🎯 Outcomes

- Full DevOps pipeline successfully deployed.
- Web application is now version-controlled, artifact-managed, and auto-deployed on every commit.

---

## 👩🏽‍💻 Author

**Emeh Tochi Doris**  
CloudOps | DevOps |   
GitHub: [@Doris-01](https://github.com/Doris-01)

---



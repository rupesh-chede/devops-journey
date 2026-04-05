# Jenkins Terraform Pipeline

## What I Did

1. Created an EC2 instance on AWS
2. Attached **Admin IAM Role** to EC2 (so no AWS keys needed)
3. Installed **Jenkins** on EC2
4. Installed **Git** on EC2
5. Installed **Terraform** on EC2
6. Created a Jenkins Pipeline with the following stages

## Pipeline Stages

- **Git Clone** — Clones this GitHub repo
- **Terraform Init** — Initializes Terraform
- **Terraform Plan** — Shows what will be created/destroyed
- **Terraform Apply / Destroy** — Runs based on parameter selected in Jenkins UI

## How to Run

1. Open Jenkins
2. Click **"Build with Parameters"**
3. Select `apply` to create infrastructure OR `destroy` to delete it
4. Click **Build**

## Notes

- No AWS credentials needed because EC2 has Admin IAM Role attached
- `action` parameter is selected from Jenkins UI before running the pipeline

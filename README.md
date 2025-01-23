# Text-Summarization-with-hugging-face-Project-
## Workflows

1. Update `config.yaml`
2. Update `params.yaml`
3. Update entity
4. Update the configuration manager in `src/config`
5. Update the components
6. Update the pipeline
7. Update `main.py`
8. Update `app.py`

## How to Run?

### Steps:

Clone the repository:

```bash
https://github.com/Shivanifeb/Text-Summarization-with-hugging-face-Project-.git
```

### Step 01: Create a Conda environment after opening the repository

```bash
conda create -n summary python=3.8 -y
```

Activate the environment:

```bash
conda activate summary
```

### Step 02: Install the requirements

```bash
pip install -r requirements.txt
```

Run the following command to start the application:

```bash
python app.py
```

--- 

---

# AWS CICD Deployment with GitHub Actions

## 1. Login to AWS Console

## 2. Create an IAM User for Deployment

### With Specific Access:

1. **EC2 Access**: For managing virtual machines.
2. **ECR Access**: Elastic Container Registry to save your Docker image in AWS.

### Deployment Description:

1. Build a Docker image of the source code.
2. Push the Docker image to ECR.
3. Launch an EC2 instance.
4. Pull the Docker image from ECR to the EC2 instance.
5. Launch the Docker container in EC2.

### Required Policies:

1. `AmazonEC2ContainerRegistryFullAccess`
2. `AmazonEC2FullAccess`

## 3. Create an ECR Repository to Store/Save the Docker Image

Save the URI: `566373416292.dkr.ecr.us-east-1.amazonaws.com/text-s`

## 4. Create an EC2 Machine (Ubuntu)

## 5. Open EC2 and Install Docker on the EC2 Machine

Optional:

```bash
sudo apt-get update -y
sudo apt-get upgrade
```

Required:

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
sudo usermod -aG docker ubuntu
newgrp docker
```

## 6. Configure EC2 as a Self-Hosted Runner

Navigate to:
`Settings > Actions > Runners > New Self-Hosted Runner`  
Choose OS and run the commands one by one.

## 7. Setup GitHub Secrets

```plaintext
AWS_ACCESS_KEY_ID=
AWS_SECRET_ACCESS_KEY=
AWS_REGION=us-east-1
AWS_ECR_LOGIN_URI=566373416292.dkr.ecr.ap-south-1.amazonaws.com
ECR_REPOSITORY_NAME=simple-app

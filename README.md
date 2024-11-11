<h1 align="center">Kidney Disease Classification using MLflow and DVC</h1>

## Workflows

1. Update config.yaml
2. Update secrets.yaml [Optional]
3. Update params.yaml
4. Update the entity
5. Update the configuration manager in src config
6. Update the components
7. Update the pipeline 
8. Update the main.py
9. Update the dvc.yaml
10. app.py

## How to run?
### STEPS:

Clone the repository

```bash
https://github.com/Aftahiislam007/Kidney_Disease_Classification
```
### STEP 01 - Create a virtual environment after opening the repository (Using `venv`)

```bash
python -m venv ./venv
```

```bash
cd venv\Scripts
```

Note - Try `./activate` instead of `activate` if using powershell terminal

```bash
activate
```

### STEP 02 - Install the requirements
```bash
pip install -r requirements.txt
```

### STEP 03 - Run the main project file
```bash
# Finally run the following command
python main.py
```
>OR

### STEP 03 - Run the project (If want to run with `dvc` command)

#### Step - 1

```bash
dvc init
```

#### Step - 2

```bash
dvc repro
```

#### Step - 3 (Optional - If want to see in `Directed Acyclic Graph (DAG)` mode)

```bash
dvc dag
```





## MLflow

- [Documentation](https://mlflow.org/docs/latest/index.html)

### MLflow install using `pip` (If needed)
```bash
pip install mlflow
```

## dagshub
- [Dagshub Website](https://dagshub.com/)

### dagshub install using `pip` (If needed)
```bash
pip install dagshub
``` 

### Update this information as per following the user type - 
 

The `MLFLOW_TRACKING_URI` is the ML flow Tracking remote link of this repository, the `MLFLOW_TRACKING_USERNAME` is the "Username" of the User and also the `MLFLOW_TRACKING_PASSWORD` is the "Personal Generated-Token" of the User.

> MLFLOW_TRACKING_URI=https://dagshub.com/user_name/repository_name.mlflow <br>
> MLFLOW_TRACKING_USERNAME=**user_name** <br>
> MLFLOW_TRACKING_PASSWORD=**personal access-token**




### Run this to export as env variables in `Git Bash` terminal:

```bash

export MLFLOW_TRACKING_URI=https://dagshub.com/Aftahiislam007/Kidney_Disease_Classification.mlflow

export MLFLOW_TRACKING_USERNAME=Aftahiislam007 

export MLFLOW_TRACKING_PASSWORD=52e4eb244e8eae6cd6c5a140e7413f13bf02852f

```



# AWS-CICD-Deployment-with-Github-Actions

## 1. Login to AWS console.

## 2. Create IAM user for deployment

###	With Specific Access

>1. **EC2 access :** It is virtual machine
>
>2. **ECR :** Elastic Container registry to save your docker image in aws


### Description: About the Deployment

>1. Build docker image of the source code
>
>2. Push the docker image to ECR
>
>3. Launch the EC2 
>
>4. Pull the image from ECR in EC2
>
>5. Lauch the docker image in EC2

### Policy:

>1. AmazonEC2ContainerRegistryFullAccess
>
>2. AmazonEC2FullAccess

	
## 3. Create ECR repo to store/save docker image

>- **Save the URI :** 307946679963.dkr.ecr.eu-north-1.amazonaws.com/kidney

	
## 4. Create EC2 machine (Ubuntu) 

## 5. Open EC2 and Install docker in EC2 Machine:
	
	
### Optinal

```bash
sudo apt-get update -y
```

```bash
sudo apt-get upgrade
```
	
### Required

```bash
curl -fsSL https://get.docker.com -o get-docker.sh
```

```bash
sudo sh get-docker.sh
```

```bash
sudo usermod -aG docker ubuntu
```	

```bash
newgrp docker
```	
	
	
## 6. Configure EC2 as self-hosted runner:
>settings > actions > runner > new self hosted runner > choose os > then run command one by one


## 7. Setup github secrets:

>AWS_ACCESS_KEY_ID=
>
>AWS_SECRET_ACCESS_KEY=
>
>AWS_REGION = eu-north-1
>
>AWS_ECR_LOGIN_URI = demo>>  307946679963.dkr.ecr.eu-north-1.amazonaws.com
>
>ECR_REPOSITORY_NAME = kidney



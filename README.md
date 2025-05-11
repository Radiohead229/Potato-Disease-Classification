# Potato-Disease-Classification
A Deep Learning Project on Potato Disease Classification using CNN and MLOPS (tf serving).

### Problem Statement
Farmers who grow potato are facing a lot of economical losses every year due to various diseases that can happen to a potato plant. There are two common diseases known as Early Blight and Late Blight. These are two serious fungal diseases affecting potatoes, and are caused by different pathogens and have distinct characteristics. Now if a farmer detects this early and apply appropriate treatment then it can save a lot of waste and prevent economical loss. The treatments for early blight and late blight are little different, so it is important to accurately identify them.

# End-to-End Project Idea
- Building a deep learning model using **CNN, tensorflow, data augumentation and tf dataset**.
  
- Exploring  tf serving and **FastAPI** for backend server and MLOPS.
  
- Model Optimization through **quantization and tensorflow lite**.
  
- Using **React JS** and **React Native** for Frontend.
  
- Deploying the model on Google Cloud Platform using Google Cloud Functions to handle inference requests.

# Data Source Used
The primary dataset for the project has been taken from kaggle [link](https://www.kaggle.com/datasets/arjuntejaswi/plant-village).

# Tools Used
- Docker Desktop
- Postman
- Pycharm
- Git
- Jupyter Notebook
- ReactJS

# Installation and Configuration
>[!Note]
>**The system is hosted on Windows 11 (64-bit) with an x64-based processor, Webpack 4, WSL enabled, and Docker Desktop installed.**

## Setup for Python and Jupyter Notebook
Step 1: Downlaod and Intsall Python from [here](https://www.python.org)

Step 2: Install the required python packages mentioned in the **"requirement.txt"** file.

Step 3: Install Jupyter Notebook via Gitbash [git setup guides](https://git-scm.com/download/win) and run the codes

```
python --version
pip --version
```
This checks if python is installed in the system. Shows version numbers. If it does not, restart terminal or reinstall Python with the PATH option checked.

```
pip install notebook
```
Wait for it to complete. This installs the classic Jupyter Notebook interface.

```
python -m notebook
```
This will start a local server in default web browser. `http://localhost:8888/tree`.


## Setup for ReactJS
Step 1: Download and Install Nodejs from [here](https://nodejs.org/en/download)

Step 2: Install NPM (Setup instructions)

Step 3: Install dependencies

`cd frontend`

changes the directory to frontend

`npm install --from-lock-json`

pulls all javascript modules that are required for the project

`npm audit fix`

Automatically finds and fixes known security vulnerabilities in project's dependencies.


Visit my project [Exploring-BI-Tools](https://github.com/Radiohead229/Exploring-BI-Tools?tab=readme-ov-file#1-installing-superset-using-docker-compose) for understanding setup guides on **Docker Desktop** installation process.[Till Step 5]


















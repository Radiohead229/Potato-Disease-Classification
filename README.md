# Potato-Disease-Classification 
A Deep Learning Project on Potato Disease Classification using CNN and MLOPS (tf serving).

### Problem Statement
Farmers who grow potato are facing a lot of economical losses every year due to various diseases that can happen to a potato plant. There are two common diseases known as Early Blight and Late Blight. These are two serious fungal diseases affecting potatoes, and are caused by different pathogens and have distinct characteristics. Now if a farmer detects this early and apply appropriate treatment then it can save a lot of waste and prevent economical loss. The treatments for early blight and late blight are little different, so it is important to accurately identify them.

# End-to-End Project Idea
- Building a deep learning model using **CNN, tensorflow, data augumentation and tf dataset**.
  
- Exploring  **TF serving** and **FastAPI** for backend server and MLOPS.
  
- Model Optimization through **quantization**.
  
- Using **React JS** for Frontend.

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

Step 3: Run the codes in your terminal to install the necessary dependencies

```
cd frontend
```
changes the directory to frontend

```
npm install --from-lock-json
```
pulls all javascript modules that are required for the project

```
npm audit fix
```
automatically finds and fixes known security vulnerabilities in project's dependencies.

Step 4: Copy the file `env.example` and save as `.env` file in the src folder.

## Setup for Docker Desktop

Visit my project [Exploring-BI-Tools](https://github.com/Radiohead229/Exploring-BI-Tools?tab=readme-ov-file#1-installing-superset-using-docker-compose) for understanding setup guides on **Docker Desktop** installation process.[Till Step 5]


## Backend Configuration 
#### FastAPI and TF serving on Docker Compose
Step 1: After installing Docker, get a docker image of Tf serving. You can either pull the image from docker desktop application from the *Search bar option* or through terminal command 
```
docker pull tensoflow/serving
```

Step 2: Create the *base path* by mapping the host directory of the project from computer to some directory (name it yourslef) inside the docker container

```
docker run -it -v C:\code\potato:/potato -p 8501:8501 --entrypoint bin/bash tensorflow/serving
```

Here `C:\code\potato` is my host directory and `/potato` is the directory i'm creating inside my docker container.

Step 3: Now run the tf  server and test your prediction model(s) using docker

```
docker run -it --rm -p 8501:8501 -v C:\code\potato:/potato tensorflow/serving --rest_api_port=8501 --model_config_file=/potato/models.config

```
Make sure your **models.config** file has the correct file path of the **docker container**.


## Frontend Configuration
In gitbash inside you frontend directory run the code 

```
npm run start
```

>[!CAUTION]
>Make sure your python system has **CORS** (cross origin resource sharing) interpreter. It is important because the frontend server is working on the port 3000 while the backend server runs at 8000. CORS allows cross port requests. Also in the gitbash if it shows `digital envelope routines::unsupported` error it is because of compatibility issue between Node.js 17+ and Webpack 4 (used by react-scripts), due to OpenSSL 3 in Node.js, therefore to fix the error type in the code in bash `export NODE_OPTIONS=--openssl-legacy-provider` and then run start again.

>[!NOTE]
>Check if network address of `.env file` is located at **localhost** and not at port 0.0.0 in case of any runtime error.


# Description
This Project primarily focuses on model training by CNN algorithm, exploration of api with tf serving, a little exploration of docker desktop and a slight understanding of web dev(html,css, js).

In newer versions of TensorFlow and Keras (specifically Keras 3), models are no longer saved in a single format that combines both the **.keras** file with the assets, variables, and saved_model.pb. Therefore, two separate saving functions are used. One for saving in **.keras** format using **model.save()** and the other for exporting a full TensorFlow **SavedModel** directory using **model.export()**. However, to reduce this, I've written a code were you can save both formats in one single call and can create a custom function that saves both the **.keras** file and the **model** directory, effectively giving you both outputs. visit my [gist](https://gist.github.com/Radiohead229/8a373c88b514e01fdc0b25bebdb1a0d4) to check out the code.

A sample overview of the directory
```
/saved_models/
    /1/
        1.keras              # Keras model file
        model/               # TensorFlow saved model folder
            saved_model.pb    # The protobuf model file
            variables/        # The model's variables
            assets/            # Any associated assests
```












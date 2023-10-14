<include a CircleCI status badge, here>

[![CircleCI](https://app.circleci.com/pipelines/github/shubhks21/project-ml-microservice-kubernetes?branch=feature%2Fcircleci.svg?style=svg)](https://app.circleci.com/pipelines/github/shubhks21/project-ml-microservice-kubernetes?branch=feature%2Fcircleci)

## Project Summary

In this project, I have applied the skills that I have acquired in this course to operationalize a Machine Learning Microservice API. 

I was given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. One can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tested my ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

### Project Instructions

My project goal was to operationalize this working, machine learning microservice using [kubernetes](https://kubernetes.io/), which is an open-source system for automating the management of containerized applications. In this project I did the following:
* Test your project code using linting
* Complete a Dockerfile to containerize this application
* Deploy your containerized application using Docker and make a prediction
* Improve the log statements in the source code for this application
* Configure Kubernetes and create a Kubernetes cluster
* Deploy a container using Kubernetes and make a prediction
* Upload a complete Github repo with CircleCI to indicate that your code has been tested

Detailed [project rubric, here](https://review.udacity.com/#!/rubrics/2576/view).

**The final implementation of the project will showcase your abilities to operationalize production microservices.**

---

## Setup the Environment

* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

## Short Explanation of Files

The repository "project-ml-microservice-kubernetes" contains the files necessary to deploy a machine learning application using Kubernetes.

### Description of files

Dockerfile: This file is used to build the Docker image for the application. It specifies the base image, installs dependencies, and copies the application code into the image.

Makefile: This file contains a set of commands that automate the build, test, and deployment processes. It provides shortcuts for common tasks, such as building the Docker image, running tests, and deploying the application.

app.py: This is the main Python file that contains the Flask application. It defines the routes and handles the requests from the users.

make_prediction.sh: This shell script sends a POST request to the running application to make a prediction. It takes a sample payload as input and returns the prediction result.

requirements.txt: This file lists all the Python dependencies required by the application. These dependencies will be installed when building the Docker image.

run_docker.sh: This shell script builds the Docker image using the Dockerfile and runs the containerized application.

run_kubernetes.sh: This shell script deploys the application to a Kubernetes cluster. It creates a deployment and a service for the application.

upload_docker.sh: This shell script tags and uploads the Docker image to Docker Hub. It requires you to provide your Docker Hub username and image name.

These files work together to containerize and deploy the machine learning application using Kubernetes.
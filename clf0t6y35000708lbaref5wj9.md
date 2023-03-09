---
title: "Deploy Springboot Microservices App into Amazon EKS Cluster using Jenkins Pipeline"
datePublished: Thu Mar 09 2023 07:50:14 GMT+0000 (Coordinated Universal Time)
cuid: clf0t6y35000708lbaref5wj9
slug: deploy-springboot-microservices-app-into-amazon-eks-cluster-using-jenkins-pipeline
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1678343273500/cd2e75fc-148b-480c-8e39-7f1022481e5b.png
tags: aws, kubernetes, jenkins, ci-cd, blogswithcc

---

---

![Animation GIF](https://cdn.hashnode.com/res/hashnode/image/upload/v1678346732265/10070d8f-eb90-4262-8ffb-5fa85a0cc4b6.gif align="center")

We will learn how to automate spring-boot microservices builds using the Jenkins pipeline and Deploy it into AWS EKS Cluster with help of the Kubernetes CLI plug-in.

We will use Springboot Microservices-based Java application. I have already created a repo with source code + Dockerfile. The repo also has Jenkinsfile for automating the following:

\- Automating builds using Jenkins  
\- Automating Docker image creation  
\- Automating Docker image upload into AWS ECR  
\- Automating Docker Containers Deployments to Kubernetes Cluster

![Deployment Architecture](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEg-CDo3r0LWddE5FLOq1w9K-N7MFfosRsf0jFVmr8oEdWRn4_NTHhgQ2eciSen6rghNi_rPWZ2N4BRTWxM9y10mhi5laXDIC5LrNY5sLBgqlxe08qzMsrMI_y3Np7VUschr79SeMuaBLiBZtiYRjMLJnw6LBbLdJV-pnb0_IGPd9yx0htmp2c7dgrqb/s899/Screen%20Shot%202022-09-04%20at%201.33.59%20PM.png align="center")

Make sure you fork my repo: [**<mark>https://github.com/Biswajit-Mohapatra2/My-SpringBoot-App.git</mark>**](https://github.com/Biswajit-Mohapatra2/My-SpringBoot-App.git)

---

# **Pre-requisites:**

1\. Amazon EKS Cluster is set up and running. Click [here](https://biswajitblogs.hashnode.dev/how-to-create-eks-cluster-in-aws-using-eksctl) to learn how to create an Amazon EKS cluster.

2\. Create an ECR repo in AWS

3. J[enkins Master is up and running](https://biswajitblogs.hashnode.dev/how-to-setup-jenkins-in-ubuntu-ec2-instance)

4\. Docker installed on the Jenkins instance

5\. Docker, Docker pipeline and Kubernetes CLI plug-ins are installed in Jenkins

![Plugin](https://1.bp.blogspot.com/-ub6WkGJ-Op0/Xt_vpFJ6seI/AAAAAAAACik/2-bcHRPt-GQuKMFTPXMl17cHoPFI52AYQCK4BGAsYHg/s920/docker-plugins.png align="center")

![](https://blogger.googleusercontent.com/img/a/AVvXsEiNDaWR1hHRZOt6G3OeUZS2EQOoNdthqj18R-kcAudsSwO7--SJ8d22J7ujPg-R5Xq8IIo9bP9XAXoWlp1ze8WB20LWl5mu0-WuPpWIKj6eEYwumv1POeS1Ax1vGVnhd0yMVSHW0DPhULNWI-DfxAk3hOYtdbTnYDozvEg8auvs4XjWGuPj5gWDZSmW=s320 align="center")

6. Install kubectl on your instance.

---

# Let's Create a Pipeline:

## **Step # 1 - Create Maven3 variable under Global tool configuration in Jenkins**

Make sure you create a Maven3 variable under the Global tool configuration

![](https://1.bp.blogspot.com/-qqqOVip7K6I/YEAxDxYsALI/AAAAAAAADUo/gqlv4lsl4x0u1lT8wf87S637h-NJHhrdwCLcBGAsYHQ/s968/maven3.png align="center")

---

## **Step #2 - Create Credentials for connecting to Kubernetes Cluster using kubeconfig**

Click on Add Credentials, and use Kubernetes configuration from the dropdown.

![](https://1.bp.blogspot.com/-Mvy6LFnLTsY/Xq-NSobh4VI/AAAAAAAACFc/Pkx9j31nxKobJySQegbx2uDD36JSNrHuACLcBGAsYHQ/s1600/add.png align="center")

**<mark>use a secret file from the drop-down.</mark>**

![](https://blogger.googleusercontent.com/img/a/AVvXsEj87Lftt4azdQg8eugpMj1YAmu9XoNC-oJsqMr5AHJMOL_dFGqIw5fzADKTocJ-E-u9KMnaDW8lrA431jm_mq0Z9R9zBRxiwIFAIuSyDGkVclUr-UnL1Bpt_O0fymsuV9GwbYyJdGLG1BPRpK8QmqZsyT6x_2CpIioRt5I3Z_-rv5jPInF49tXsjghaIw=s834 align="center")

**<mark>Execute the below command to log in as jenkins user.</mark>**

```bash
sudo su - jenkins
```

**<mark>You should see the nodes running in the EKS cluster.</mark>**

```bash
kubectl get nodes
```

![](https://blogger.googleusercontent.com/img/b/R29vZ2xl/AVvXsEiWKwQKkodHDUTMwiiduNmlDg0CbpkRvPD7xQLIizKvnoMroaeIq1Di1YsJ17cpE5aSlpMtnMWOzAZNiowSIhygwdc-Z8USCwDPNO57q2t-8WfuAfjqOAqXunJ9OgKwd1ts7J4okIWg5BQ0VLcR6sEwV5G1r3Bl0tLSAwUffFq9xU-FwqM4g1EpQvSj/s1600/Screen%20Shot%202022-05-13%20at%207.26.51%20PM.png align="center")

**<mark>Execute the below command to get kubeconfig info, and copy the entire content of the file:</mark>**

```bash
cat /var/lib/jenkins/.kube/config
```

![](https://blogger.googleusercontent.com/img/a/AVvXsEh07GG01S0ezTnehqzoCjlHugN94T9-xwwv2ErJPG0I268sDgSANIMYcfFxV2n84TcSNos7FVprINGC_NlXiCBS5_Pgfybv81ccRlwPaUDO9AJVeU85ibtaD6VMlQ3OhptxEgqpxTmT9Hv3lcPxCAxkw3Uxc3kjLJnaj5QwnQLLg16aDLaDILUE5zZ4=s2376 align="center")

<mark>Open your text editor or notepad, copy and paste the entire content and save in a file. We will upload this file.</mark>

![](https://blogger.googleusercontent.com/img/a/AVvXsEgNnKliu1KL-cn_Ze5GgmrzCX6TUfs_TUC5xKu0P3q-QhfaN97pV_DRmZ-4Sh-zrbHMEl--CwHHC1MzJfyk9fh0ezzXOcExilGR6rVPsNISfEfXNadRplfeY9z3sAJ8ErXiBr5mx7I1OXO2CAH0b70tP1873KzRjLI5jzq2NW1T8WJPltq06bLGi_tACQ=s896 align="center")

<mark>Enter ID as K8S and choose File and upload the file and save.</mark>

![](https://blogger.googleusercontent.com/img/a/AVvXsEitDtvjqpqYnopwU3Oi4C46zEST16kIPVW8MtIeRStLWPe3Lfhx9pNTMnAXRWV3mdBF5ThlakzAGEGmmgbFzhbvIQJSxO_MTxbljAcAaOBWwa4nd1IdYvTtNEt4pTwiBqkNZzs0FLS1gq7on8TAS2vaDbVJSDuLYKXmkFtAE21BSiFMAL9LGo0LApmenw=s884 align="center")

<mark>Enter ID as K8S and choose to enter directly and paste the above file content and save.</mark>

---

## **Step # 3 - Create a pipeline in Jenkins**

<mark>Create a new pipeline job.</mark>

![](https://1.bp.blogspot.com/-pk3H4-qXqUg/Xt_xYAAnbiI/AAAAAAAACjw/tIymD_gtPUsKFOn72WsjlUTHkGJHT7fXACK4BGAsYHg/s682/myk8sjob.png align="center")

---

## **Step # 4 - Copy the pipeline code from below:**

Make sure you change the **<mark>yellow</mark>** highlighted values below as per your settings:  
Your docker user id should be updated.  
<mark>your registry credentials ID from Jenkins from step # 1 should be copied.</mark>

> pipeline {
> 
> tools {
> 
> maven 'Maven3'
> 
> }
> 
> agent any
> 
> environment {
> 
> registry = "<mark>account_id</mark>.dkr.ecr.us-east-2.amazonaws.com/my-docker-repo"
> 
> }
> 
> stages {
> 
> stage('Cloning Git') {
> 
> steps {
> 
> checkout(\[$class: 'GitSCM', branches: \[\[name: '\*/main'\]\], doGenerateSubmoduleConfigurations: false, extensions: \[\], submoduleCfg: \[\], userRemoteConfigs: \[\[credentialsId: '', url: '[https://github.com/akannan1087/springboot-app](https://github.com/akannan1087/springboot-app)'\]\]\])
> 
> }
> 
> }
> 
> stage ('Build') {
> 
> steps {
> 
> sh 'mvn clean install'
> 
> }
> 
> }
> 
> // Building Docker images
> 
> stage('Building image') {
> 
> steps{
> 
> script {
> 
> dockerImage = docker.build registry
> 
> }
> 
> }
> 
> }
> 
> // Uploading Docker images into AWS ECR
> 
> stage('Pushing to ECR') {
> 
> steps{
> 
> script {
> 
> sh 'aws ecr get-login-password --region us-east-2 | docker login --username AWS --password-stdin <mark>account_id</mark>.dkr.ecr.us-east-2.amazonaws.com'
> 
> sh 'docker push <mark>account_id</mark>.dkr.ecr.us-east-2.amazonaws.com/my-docker-repo:latest'
> 
> }
> 
> }
> 
> }
> 
> stage('K8S Deploy') {
> 
> steps{
> 
> script {
> 
> withKubeConfig(\[credentialsId: '<mark>K8S</mark>', serverUrl: ''\]) {
> 
> sh ('kubectl apply -f  eks-deploy-k8s.yaml')
> 
> }
> 
> }
> 
> }
> 
> }
> 
> }
> 
> }

---

## **Step # 5 - Build the pipeline**

<mark>Once you create the pipeline and changes values per your configuration, click on Build now:</mark>

![Pipeline Build](https://blogger.googleusercontent.com/img/a/AVvXsEi_H6PgEVPk7Cu8iikw6Ac8wtfABBU5AjyimjzRCSCkoF4ePKYSXCljhlL5OeBMC6WczqwXZogi-t_y5F_zMe7Mn0zKMFKLdQ-lNfaFTkvRYOtQeAKBTmp45S8h2omnPNdc-MUj_p2K1aNK2da4fLB-cPSe9o50qHYc50j4Y29AJV7c8r3NKzDRyHnL=s1628 align="center")

---

## **Step # 6 - Verify deployments to K8S**

```bash
kubectl get pods
```

![](https://1.bp.blogspot.com/-xPmhS4ehKKM/X9lOutozp5I/AAAAAAAADLc/8EotGJ1lUOkLB0I0riVX9qVNhsUZhZUbgCLcBGAsYHQ/s583/podd2.png align="center")

```bash
kubectl get deployments
```

![](https://1.bp.blogspot.com/-3rBuEPQN6JE/X9lOuq2G65I/AAAAAAAADLY/741eWCCWbzAvvb9d4WisbDYVi9tEPZqHwCLcBGAsYHQ/s535/d1.png align="center")

```bash
kubectl get services
```

![](https://1.bp.blogspot.com/-Uwqj5y55nmU/X9lOSTh-xVI/AAAAAAAADLQ/lEJl0Yynvh0ZQSB71pBaiy87Qs74duhywCLcBGAsYHQ/s974/angular.png align="center")

---

## **Step # 7 - Access SpringBoot App in the K8S cluster.**

Once the build is successful, go to the browser and enter the master or worker node public IP address along with the port number mentioned above

<mark>http://loadbalancer_ip_address</mark>

<mark>You should see a page like below:</mark>

![Final output](https://cdn.hashnode.com/res/hashnode/image/upload/v1678346176984/fb2ed1b3-8c03-4193-9b2d-d2608f0cbfcc.jpeg align="center")

**<mark>Note:</mark>**

Make sure you fork my repo [<mark>https://github.com/Biswajit-Mohapatra2/My-SpringBoot-App.git</mark>](https://github.com/Biswajit-Mohapatra2/My-SpringBoot-App.git) and make changes in **<mark>eks-deploy-k8s.yaml</mark>** to pull Docker image from your AWS ECR repo.

![Deployment image](https://cdn.hashnode.com/res/hashnode/image/upload/v1678345986285/4c699f4a-461b-41e8-ad1a-aa238fcd6e03.png align="center")

---

![GIF](https://cdn.hashnode.com/res/hashnode/image/upload/v1678346795151/2d7005f7-581c-4bd9-a738-eebb242f03da.gif align="center")

cheers🤟

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678347079565/df69a4e3-611f-4b92-bc6f-f3e53a24d25f.gif align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1678347122031/e32582a0-eede-4ae6-89ec-47b8e60947c0.gif align="center")
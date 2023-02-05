# Dockerize Python App

---

# Context

We will learn how to automate Docker builds using Jenkins. We will use a **Python-based application.** I have already created a repo with source code + Dockerfile. We will be creating a **Declarative Jenkins pipeline** for automating builds.

![Architecture](https://1.bp.blogspot.com/-vkXWMMiJuas/X20JaNQtFrI/AAAAAAAADCw/tbe2Mc51e5Y1Qo-oXUuyJvxY0Icd2cCtACLcBGAsYHQ/s1298/jenkins%2Bdockerhub.png align="center")

\- Automating builds.  
\- Automating Docker image creation.  
\- Automating Docker image upload.  
\- Automating Docker container provisioning.

# **Pre-requisites:**

1\. [**<mark>Jenkins</mark>**](https://biswajitblogs.hashnode.dev/how-to-setup-jenkins-in-ubuntu-ec2-instance) <mark> is up and running</mark>  
2\. <mark>Docker installed on Jenkins instance and configured</mark>.  
3\. <mark>Docker plug-in installed in Jenkins</mark>  
4\. <mark>user account setup in https://cloud.docker.com</mark>  
5\. <mark>port 8096 is opened up in firewall rules</mark>.

![Installing docker pipeline plugins](https://1.bp.blogspot.com/-ub6WkGJ-Op0/Xt_vpFJ6seI/AAAAAAAACik/2-bcHRPt-GQuKMFTPXMl17cHoPFI52AYQCK4BGAsYHg/s920/docker-plugins.png align="center")

---

# Let's Start with Jenkins

### **Step #1 - Create Credentials for Docker Hub**

<mark>Go to your Jenkins where you have installed Docker as well. Go to credentials --&gt;</mark>

![](https://1.bp.blogspot.com/-XJG5VsPD8Qo/Xq-M6yxaHZI/AAAAAAAACFQ/vXDXsbe0hyM91GM0Bh5VNZXsGasOmFWeACLcBGAsYHQ/s1600/crdentials.png align="left")

<mark>Click on Global credentials</mark>

![](https://1.bp.blogspot.com/-04oZVUbk5ZY/Xq-NShoX-XI/AAAAAAAACFY/-t8z6KhrGfkaGivRrGk_IOO8-L9MHJhIwCLcBGAsYHQ/s1600/global.png align="center")

<mark>Click on Add Credentials</mark>

![](https://1.bp.blogspot.com/-Mvy6LFnLTsY/Xq-NSobh4VI/AAAAAAAACFc/Pkx9j31nxKobJySQegbx2uDD36JSNrHuACLcBGAsYHQ/s1600/add.png align="center")

<mark>Now Create an entry for Docker Hub credentials</mark>

![](https://1.bp.blogspot.com/-aSBa_ebTebQ/Xq-N58ikwdI/AAAAAAAACFs/mbrp_V-Z_B0AYq1i9vdVeTybm_M5BZjsQCLcBGAsYHQ/s1600/user.png align="center")

Make sure you take note of the ID as circled below:

![](https://1.bp.blogspot.com/-9ne6aQjxrNY/Xq-OeqV2rpI/AAAAAAAACF0/Lk3RdKyLiuch30Nf-ZPDJj9smeqRXzHDwCLcBGAsYHQ/s1600/id1.png align="center")

### **Step # 2 - Create a Jenkins pipeline**

![](https://1.bp.blogspot.com/-r0513ohKbYQ/Xq-UkLCFTJI/AAAAAAAACGU/A9SLAF0F5F0qJbQQtpfHEDgiAnopRrh0QCLcBGAsYHQ/s1600/pipeline.png align="center")

### **Step # 3 - Write the pipeline code**

<mark>Make sure you change the </mark> **<mark>Emoji highlighted</mark>** <mark> values below:<br>Your docker user id should be updated.<br>your registry credentials ID from Jenkins from step # 1 should be copied.</mark>

```json
pipeline {
    agent any 
    environment {
        //once you sign up for Docker hub, use that user_id here
        registry = "your_docker_user_id✍️/mypythonapp"
        //- update your credentials ID after creating credentials for connecting to Docker Hub
        registryCredential = 'fa32f95a-2d3e-4c7b-8f34-11bcc0191d70✍️' 
                              //use your own dockercredential ID
    }
    
    stages {
        stage('Cloning Git') {
            steps {
                checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '', url: 'https://bitbucket.org/biswajitmoahapatra/mypythonrepo']]])       
            }
        }
    
    // Building Docker images
    stage('Building image') {
      steps{
        script {
          dockerImage = docker.build registry
        }
      }
    }
    
     // Uploading Docker images into Docker Hub
    stage('Upload Image') {
     steps{    
         script {
            docker.withRegistry( '', registryCredential ) {
            dockerImage.push()
            }
        }
      }
    }
    
     // Stopping Docker containers for cleaner Docker run
     stage('docker stop container') {
         steps {
            sh 'docker ps -f name=mypythonappContainer -q | xargs --no-run-if-empty docker container stop'
            sh 'docker container ls -a -fname=mypythonappContainer -q | xargs -r docker container rm'
         }
       }
    
    
    // Running Docker container, make sure port 8096 is opened in Your VM
    stage('Docker Run') {
     steps{
         script {
            dockerImage.run("-p 8096:5000 --rm --name mypythonappContainer")
         }
      }
    }
  }
}
```

### **Step # 4 - Click on Build - Build the pipeline**

<mark>Once you create the pipeline and change values per your Docker user id and credentials ID, click on&nbsp;</mark> **<mark>Save and Apply.</mark>** <mark> Then Click </mark> **<mark>Build</mark>** <mark> Option.</mark>

![](https://1.bp.blogspot.com/-unjvlO0qHMc/Xq-VmOCbBgI/AAAAAAAACGg/yUpuPTCychUqKeVpAO7j3H8jhw-71b9gQCLcBGAsYHQ/s1600/pipeline%2Bview.png align="center")

### **Step # 5 - Access Python App**

<mark>Once the build is successful, go to the browser and enter http://public_dns_name:8096</mark>

<mark>You should see the page like below:</mark>

![](https://1.bp.blogspot.com/-cx4yt2hGWC8/X20mR-qGtYI/AAAAAAAADDA/439L5Aidaqw2KREdxifz3m7fwId8gFRqQCLcBGAsYHQ/s1482/pythonapp.png align="center")

---

# Conclusion

<mark>Congratulations you successfully completed your first project.</mark>

<mark>Your Pipelining Project is done🤟🤟...</mark>

<mark>Enjoy!!</mark>

**~Biswajit Mohapatra**
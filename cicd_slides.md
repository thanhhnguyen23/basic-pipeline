---
theme: gaia
_class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
marp: false
---

![bg left:50% 80%](https://www.jenkins.io/images/logos/jenkins/jenkins.svg)

# **Basic CI/CD Pipeline with Jenkins**

https://www.jenkins.io/

---

## Case Study

* Client have a portfolio of web applications that are somewhat unstable due to frequency of changes to the source code

* Client would like to implement automation to lower application deployment overhead

### Solution
* Build out flexible CI/CD pipelines for each web application in portfolio

---

# CI/CD pipeline overview

![bg bottom:90% 90%](https://www.guru99.com/images/1/091318_0510_JenkinsPipe1.png)

---


# Jenkins Setup on Linux
```markdown

$ apt install docker -y # install docker 

$ docker pull jenkins/jenkins:lts-jdk11 # pull docker jenkins image

$ docker run -p 8080:8080  jenkin/jenkins:lts-jdk11 # run latest jenkins image via docker

$ docker run -p 8080:8080 -p 5000:5000 jenkins/jenkins:lts-jdk11 # launch jenkins via docker
```
---

# jenkins configurations in a container (via docker)
```bash
$ docker run -p 8080:8080 -p 5000:5000 jenkins/jenkins:lts-jdk11 # launch jenkins via docker
```

---
## step 1: copy admin from command line

![bg top:50% 50%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/01.png?raw=true)

---

## step 2: launch web browser: `localhost:8080` > paste admin password

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/02.png?raw=true)

---

## step 3: select first opion

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/03.png?raw=true)

---

## step 4: wait for default configurations to apply

![bg bottom:20% 40%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/04.png?raw=true)

---

## step 5: accept default user `admin` settings

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/05.png?raw=true)

---

## step 6: save and finish

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/06.png?raw=true)

---

# First Pipeline Workflow

* 1. open web browser: `locahost:8080`
* 2. new item > enter item name "my-basic-pipeline" > select pipeline > OK
* 3. `Pipeline` tab > Script text box
* 4. copy and paste contents of `basic pipeline example` from previous slide
* 5. `Build Now`

---

## step 1: New Item

![bg bottom:70% 70%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/A.png?raw=true)

---

## step 2: 

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/B.png?raw=true)

---

## step 3: click on Pipeline tab

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/C.png?raw=true)

---

## step 4: click on Pipeline tab

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/D.png?raw=true)

---

# Basic Pipeline Example
>Jenkinsfile (Declarative Pipeline)
```
pipeline {
    agent any 
    stages {
        stage('Build') { 
            steps {
            	echo 'building application'
            }
        }
        stage('Deploy') { 
            steps {
            	echo 'deploy application'
            }
        }
        stage('Test') { 
            steps {
            	echo 'testing application'
            }
        }
        stage('Release') { 
            steps {
            	echo 'production release'
            }
        }
    }
}
```
---

## step 5: `Build New`

![bg bottom:60% 60%](https://github.com/thanhhnguyen23/basic-pipeline/blob/main/E.png?raw=true)

---


# References
* https://www.jenkins.io/pipeline/getting-started-pipelines/
* https://docs.docker.com/engine/install/
* https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
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
$ apt install docker -y # install dependencies (jenkins/docker)
$ docker pull jenkins/jenkins:lts-jdk11
$ docker run -p 8080:8080  jenkin/jenkins:lts-jdk11
$ docker run -p 8080:8080 -p 5000:5000 jenkins/jenkins:lts-jdk11

```

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

# DEMO Notes:

* 1. open web browser: `locahost:8080`

* 2. new item > enter item name "my-basic-pipeline" > select pipeline > OK

* 3. `Pipeline` tab > Script text box

* 4. copy and paste contents of `basic pipeline example` from previous slide

* 5. `Build Now`

---

# References
* https://www.jenkins.io/pipeline/getting-started-pipelines/
* https://docs.docker.com/engine/install/
* https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
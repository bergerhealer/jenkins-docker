# Jenkins Docker image for JDK19
This repository hosts some minor modifications to build a Jenkins Docker debian image for JDK19

## Building
Go to the root directory and run:

`sudo make build-debian_jdk19`

This will build:

`docker.io/jenkins/jenkins:2.356-jdk19`

## Change jenkins version
You can change the version of jenkins built by passing environment variables:

```
sudo \
    JENKINS_VERSION="2.375.3" \
    JENKINS_SHA="d56065f1e5c4323fec36a96abf7710b2451e34bc4fb9da179e7df129a4ccc1ac" \
    make build-debian_jdk19
```

Which builds:

`docker.io/jenkins/jenkins:2.375.3-jdk19`

Available versions and their sha1 hashes: [https://www.jenkins.io/download/](https://www.jenkins.io/download/)

## Change jenkins home/uid/gid
You can also set:
- JENKINS_HOME: Where the main jenkins workspace is located at inside the docker image
- JENKINS_UID: What UID is assigned to the jenkins user. Can match your system with $(id -u jenkins)
- JENKINS_GID: What GID is assigned to the jenkins user group. Can match your system with $(id -g jenkins)

## This is a Fork!
Fork of: [https://github.com/jenkinsci/docker](https://github.com/jenkinsci/docker)

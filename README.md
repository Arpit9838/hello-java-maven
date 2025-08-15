# Task 8: Run a Simple Java Maven Build Job in Jenkins

## Objective
Learn how to use Jenkins to build a simple Java application using Maven — a first step into CI/CD automation.


## Tools Used
- Jenkins (LTS version, running in Docker)
- Java JDK 8/11
- Maven (installed via Jenkins Global Tool Configuration)
- GitHub (source code repository)



## Repository
Java Maven Hello World project:  

## Steps Performed

### 1. Start Jenkins in Docker

docker run -d --name jenkins \ -p 8080:8080 -p 50000:50000 \ jenkins/jenkins:lts

docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
Open Jenkins at: http://localhost:8080

2. Configure Maven in Jenkins
Go to Manage Jenkins → Global Tool Configuration

Under Maven Installations:

Name: Maven

Install Automatically: ✅

Version: 3.8.6

Save.

3. Create Jenkins Job
New Item → Name: hello-java-maven → Freestyle Project → OK

Source Code Management:

Git Repository URL:
https://github.com/Arpit9838/hello-java-maven

Branch: main

Build Section:

Build Step: Invoke top-level Maven targets

Maven Version: Maven

Goals: clean package

Save.

4. Run the Build
Click Build Now.

Check the Console Output for:


[INFO] BUILD SUCCESS


Outcome
Successfully built a Java Maven project using Jenkins.

Learned how Jenkins integrates with Maven for automated builds.

Verified output from Jenkins console.

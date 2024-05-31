# Git, Maven, Jenkins, Sonarqube, Nexus
## Maven
- link project : https://github.com/aymendr/vprofile-project
### Installation
#### Ubuntu 22.04 LTS
- sudo apt update
- sudo apt search jdk
- sudo apt install openjdk-11-jdk
- sudo apt install maven
- Maven Download link: https://maven.apache.org/download.cgi
- Copy link address : https://dlcdn.apache.org/maven/maven-3/3.9.7/binaries/apache-maven-3.9.7-bin.zip
- wget https://dlcdn.apache.org/maven/maven-3/3.9.7/binaries/apache-maven-3.9.7-bin.tar.gz
- tar xvzf  apache-maven-3.9.7-bin.tar.gz
- or sudo apt install maven
- Move maven folder to /opt
- clone projet with git : git clone https://github.com/aymendr/vprofile-project

## Jenkins
### Installation
- link : https://www.jenkins.io/doc/book/installing/

## Nexus
### Installation
- Download sonatype nexus artifactory: https://help.sonatype.com/en/download-archives---repository-manager-3.html
- Installation : https://help.sonatype.com/en/installation-methods.html
- Extract folder and navigate to <sonatype>/bin/<distribution>. Start nexus server : nexus.exe /run
- Install **Nexus Artifact Uploader** Jenkins plugin

## Sonarqube
### Installation
- Download link : https://www.sonarsource.com/products/sonarqube/downloads/success-download-community-edition/
- Start Sonarqube from <sonar-folder>\bin\windows-x86-64\StartSonar.bat or install the service with the command :
``` SonarService.bat install ```
- or from the command line
- On Windows, execute: ```C:\sonarqube\bin\windows-x86-64\StartSonar.bat```
- On other operating systems, as a non-root user execute: ```/opt/sonarqube/bin/<OS>/sonar.sh console```
- Follow server logs with the command ``` tail -f <sonar-folder>/logs/sonar.log ```
- For more details about managing sonarqube service see documentation : https://docs.sonarsource.com/sonarqube/latest/setup-and-upgrade/configure-and-operate-a-server/operating-the-server/
- On Jenkins install **SonarQube Scanner** plugin
- access sonarqube server on **localhost:9000** with admin/admin credentials
- change default password once logged in
- Generate a token for jenkins form ** Profile icon --> My Account -->  Security --> Generate token : squ_3e7de4285c4bf95e1e2216ea80b8a767d2f81705
- In Jenkins --> Manage Jenkins --> System --> SonarQube installations --> Give a name, Server URL, and Server authentication token (secret text corresponding to sonarqube token created)
- In Jenkins --> Manage Jenkins --> Tools --> SonarQube Scanner installations --> set install automatically
- Configure sonarqube Plugin within maven project : https://docs.sonarsource.com/sonarqube/latest/analyzing-source-code/scanners/sonarscanner-for-maven/

## Integration of tools within Jenkins
- Install **pipeline maven integration** et **Pipepline Utility Steps** plugins

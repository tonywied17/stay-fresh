# Manually deploying a web app with Tomcat 10

this guide will help you deploy your .war web app on an EC2 with Tomcat.

1. ssh into your EC2.
2. make sure that you've updated everything.
``` sh
sudo yum update
```
3. install java, maven, git, and tomcat on your EC2 using the yum package manager.
``` sh
# java 8
sudo yum install java-1.8.0-openjdk-devel -y

# maven
sudo wget http://repos.fedorapeople.org/repos/dchen/apache-maven/epel-apache-maven.repo -O /etc/yum.repos.d/epel-apache-maven.repo
sudo sed -i s/\$releasever/6/g /etc/yum.repos.d/epel-apache-maven.repo
sudo yum install -y apache-maven

# git
sudo yum install git -y

# tomcat
sudo wget https://dlcdn.apache.org/tomcat/tomcat-10/v10.0.22/bin/apache-tomcat-10.0.22.tar.gz
tar -zxf apache-tomcat-10.0.22.tar.gz
```
4. next, we'll use git to pull our web app.
``` sh
# if you haven't cloned it yet
git clone https://github.com/220620-java/p1-web-yourteamname.git

# if you already have and you're pulling changes
cd p1-web-yourteamname/
git pull origin main
```
5. if you were using a .gitignore to ignore your database.properties, you will need to re-create that file again locally on the EC2.
``` sh
touch ~/p1-web-yourteamname/src/main/resources/database.properties

# open the file with your text editor of choice:
nano ~/p1-web-yourteamname/src/main/resources/database.properties
vim ~/p1-web-yourteamname/src/main/resources/database.properties
```
6. now, we can package our application as a .war using maven. make sure you're in the same folder where your pom.xml is when you run your maven command.
``` sh
# if you don't want to run your tests first
mvn clean package

# if you want to require your tests to pass before you can package it
mvn clean test package
```
7. let's copy/move the .war file into the tomcat webapps folder so that it can be deployed.
``` sh
# if your src and pom.xml were top-level in the repository
cp target/project-name-1.0.0-SNAPSHOT.war ../apache-tomcat-10.0.22/webapps

# if your src and pom.xml were inside the project folder in the repository (for future reference, that is bad practice)
cp target/project-name-1.0.0-SNAPSHOT.war ../../apache-tomcat-10.0.22/webapps
```
8. now, we can get tomcat up and running.
``` sh
sudo sh ~/apache-tomcat-10.0.22/bin/startup.sh
```
9. your application is running now! go and add a Custom TCP rule for port 8080 on your EC2's security group that allows All traffic (ipv4).
10. you can send requests to your app using the public IP or DNS from your computer.
    - the URL will be something like `11.111.11.111:8080/your-app-0.0.1-SNAPSHOT/your-app/pets`
11. make sure that your EC2 has access to the RDS that it's using so that your application can connect to the database. see the [EC2 to RDS communication guide](./ec2-to-rds-comm.md) to set this up if you haven't already. you only need the first section; everything else is optional.
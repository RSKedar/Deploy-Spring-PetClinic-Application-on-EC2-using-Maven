# Deploy-Spring-PetClinic-Application-on-EC2-using-Maven

This project demonstrates how to deploy a Spring Boot application (Spring PetClinic) on an AWS EC2 Linux instance using Maven.

The application source code was cloned from GitHub, built using Maven to generate a JAR file, and then executed on the EC2 instance. The application runs on port 8080 and can be accessed using the EC2 public IP address.

This project demonstrates how developers deploy Java applications in a cloud environment using AWS infrastructure.

Technologies Used

AWS EC2

Linux (Amazon Linux)

Java 17

Maven

Git

Spring Boot

Project Architecture
User Browser
      │
      ▼
EC2 Public IP
      │
      ▼
Spring Boot Application
(Spring PetClinic)
      │
      ▼
Java Runtime Environment


Step 1: Launch EC2 Instance

Created an EC2 instance with the following configuration:

OS: Amazon Linux

Instance Type: t2.micro

Security Group:

SSH → Port 22

HTTP → Port 8080

Step 2: Install Java

Install Java 17 on EC2:

sudo yum install java-17-amazon-corretto -y

Verify installation:

java -version


Step 3: Install Git
sudo yum install git -y

Verify:

git --version


Step 4: Clone Spring PetClinic Repository
git clone https://github.com/spring-projects/spring-petclinic.git

Move to project directory:

cd spring-petclinic



Step 5: Build Application using Maven
./mvnw clean package

Maven downloads dependencies and builds the application.

Output JAR file:

target/spring-petclinic-4.0.0-SNAPSHOT.jar

Build Status:

BUILD SUCCESS



Step 6: Run the Application
java -jar target/spring-petclinic-4.0.0-SNAPSHOT.jar

Spring Boot starts the embedded Tomcat server.

Logs show:

Tomcat started on port 8080
Started PetclinicApplication


Step 7: Access the Application

Open browser and access:

http://EC2-Public-IP:8080

Example:

http://3.235.129.129:8080

The Spring PetClinic application UI is displayed successfully.


Security Group Configuration

Inbound Rules:

Type	Port
SSH	22
Custom TCP	8080

This allows external users to access the application.

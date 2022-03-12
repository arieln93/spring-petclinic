# Spring-PetClinic sample appliation with Jenkins pipleline

This project is originally forked from: https://github.com/spring-projects/spring-petclinic

## Prerequisites
In order to run this project, you need to have the following installed on your local machine:
* Git
* Docker
* Java version 8 or 11
* Jenkins
* Maven

Notice that this project is configured to be running on port 8080, so if you already have Jenkins configured to listen to this port, you can change it using the following steps:
1. Go to the directory where you installed Jenkins (probably Program Files/Jenkins)
2. Open the Jenkins.xml configuration file.
3. Set the `--httpPort` variable with the new port number.
4. Restart your Jenkins server.

## How to run
### Step 1: Clone the project
Clone the project and validate that you can run it on your machine without any errors, using the following commands: 
```
git clone https://github.com/talitz/spring-petclinic-jenkins-pipeline.git
cd spring-petclinic
./mvnw package
java -jar target/*.jar
```
Now browse to http://localhost:8080/ and validate you can see the application running:
<img width="1042" alt="petclinic-screenshot" src="https://cloud.githubusercontent.com/assets/838318/19727082/2aee6d6c-9b8e-11e6-81fe-e889a5ddfded.png">

### Step 2: Creat a pipeline
Open Jenkins on your local machine, and create a new pipeline with this repo link.

In the job configiration, under 'Pipeline', choose "Pipeline script from SCM" and paste this repo link.

Save the job, then enter it and click 'Build now', and wait for the buied to finish successfuly.

The docker image is now pushed to `arieln993/petclinic:latest`, the link to DockerHub is: https://hub.docker.com/r/arieln993/petclinic

### Step 2: Run docker image
In order to run it, first pull it from the DockerHub repo:
```docker pull arieln993/petclinic:latest```

Then run it using the following command:
```docker run -p 8080:8080 arieln993/petclinic```

Now, browse into ```localhost:8080``` and you should expect to see the pet clinic application app and running! :)

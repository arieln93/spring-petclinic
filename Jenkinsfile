#!groovy
pipeline {
    agent any
    stages {
        stage('Clone the repo') {
            steps {
                git 'https://github.com/arieln93/spring-petclinic.git'
            }
        }
        stage('Compile the code') {
            steps {
                sh 'mvn compile'
            }
        }
        stage('Run the tests') {
            steps {
                sh 'mvn test' 
            }
        }
        stage('Package') {
            steps {
                sh 'mvn package' 
            }      
        }
        stage('Build coker image') {
            agent any
            steps {
                sh 'docker build -t arieln993/petclinic:latest .'
            }
        }
        stage('Push docker image') {
            agent any
            steps {
                sh 'docker push arieln993/petclinic:latest'
            }
        }
        stage('Upload to Artifactory') {
          agent {
            docker {
              image 'releases-docker.jfrog.io/jfrog/jfrog-cli-v2-jf jf -v'
            }
          }
          steps {
            sh 'jfrog rt upload --url https://arieln993.jfrog.io/artifactory/petclinic/ target/*.jar petclinic/'
          }
        }
    }
}

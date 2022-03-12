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
    }
}
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
                sh './mvnw compile'
            }
        }
        stage('Run the tests') {
            steps {
                sh './mvnw test' 
            }
        }
        stage('Package') {
            steps {
                sh './mvnw package' 
            }      
        }   
    }
}
#!groovy
pipeline {
    agent any
    stages {
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
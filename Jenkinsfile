#!groovy
pipeline {
    agent none
   stages {
    stage('Clone the repo') {
      steps {
        git 'https://github.com/arieln93/spring-petclinic.git'
      }
    }    
    stage('Maven package') {
      agent {         
       docker {          
         image 'maven:3.5.0'         
     }       
  }       
  steps {
       sh './mvnw package'
       }
     }
   }
 }
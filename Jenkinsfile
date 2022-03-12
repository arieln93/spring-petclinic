#!groovy
pipeline {
    agent none
   stages {     
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
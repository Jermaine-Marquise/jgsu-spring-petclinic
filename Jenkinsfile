#!groovy
pipeline {
   agent none
  stages {
   stage('Maven Install') {
       agent {
       docker {
	   image 'maven:3.5.0'
        }
      }
      steps {
	sh 'mvn clean install -Dcheckstyle.skip -DoutputDirectory=/home/jenkins/workspace/spring-petclinic-docker/'
      }
    }
  stage('Docker Build') {
    	agent any
      steps {
      	sh 'docker build -t jermaine-marquise/spring-petclinic:latest .'
      }
    }
  }
}

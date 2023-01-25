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
      	sh 'mvn clean install'
      }
    }
    stage('Build Docker Image') {
    	agent any
      steps {
      	sh 'docker build -t ciarafennessy/qa-petclinic-team2:latest .'
      }
    }
  }
}
pipeline {
	agent any
  tools{
    maven 'Maven-3.8.7'
  }
  stages{
    stage('Build Maven'){
      steps{
        checkout scmGit(branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Kiishi25/Team2-Final-Project.git']])
        sh 'mvn clean install'
      }

    }
  }
}

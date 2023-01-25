pipeline {
	agent any
  tools{
    maven 'maven_3_8_7'
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

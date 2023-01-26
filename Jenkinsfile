pipeline {
	agent any
  tools{
    maven '3.8.7'
  }
  stages{
    stage('Build Maven'){
      steps{
        checkout scmGit(branches: [[name: '*/jenkins']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Kiishi25/Team2-Final-Project/tree/jenkins']])
        dir("Team2-Final-project") {
            sh 'mvn clean install'
                    }
      }

    }
  }
}


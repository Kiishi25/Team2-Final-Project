pipeline {
	agent any
  tools{
    maven '3.8.7'
  }
  stages{
    stage('Build Maven'){
      steps{
        checkout scmGit(branches: [[name: '*/jenkins']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Kiishi25/Team2-Final-Project/tree/jenkins']])
        dir('/job/pet-clinic-pipeline/16/execution/node/3/ws/spring-petclinic-rest/pom.xml') {
            sh 'mvn clean install'
                    }
      }

    }
  }
}


pipeline {
	agent any
  tools{
    maven '3.8.7'
  }
  stages{
    stage('Build Maven'){
      steps{
        checkout scmGit(branches: [[name: '*/jenkins']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Kiishi25/Team2-Final-Project.git']])
        dir("/job/pet-clinic-pipeline/14/execution/node/3/ws/spring-petclinic-rest/pom.xml") {
            sh 'mvn clean install'
                    }
      }

    }
  }
}


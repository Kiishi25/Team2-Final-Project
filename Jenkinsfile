pipeline {
	agent any
  tools{
    maven '3.8.7'
  }
  stages{
    stage('Build Maven'){ 
      steps{
        checkout scmGit(branches: [[name: '*/jenkins']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/Kiishi25/Team2-Final-Project.git']])
            sh 'mvn clean install'
            System.setProperty("org.jenkinsci.plugins.durabletask.BourneShellScript.HEARTBEAT_CHECK_INTERVAL", "3800");:


                    }
      }

    }
    stage('Test'){
                steps{
                sh 'mvn clean test'
                    }
                }

    stage('Build Docker Image'){
                steps{
                  
                  script{
                    sh 'docker build -t kiishi25/spring-petclinic:latest .'
                        }
              
                }
            }
    stage('Login and Push image to Hub'){
                steps{
                    script{
                        withCredentials([string(credentialsId: 'DockerHubPwd', variable: 'DockerHubPwd')]) {
                            sh 'docker login -u kiishi25 -p ${DockerHubPwd}'
                        }
                        sh 'docker push kiishi25/spring-petclinic:latest'
                    }
                }
            }

stage("Deploy to cluster - docker swarm"){

}

stage('Remove image locally'){
                steps{
                    sh 'docker rmi -f kiishi25/spring-petclinic:latest'
                }
            }
}
  



pipeline{

agent any

triggers{
pollSCM('* * * * *')
}

options{
timestamps()
buildDiscarder(logRotator(artifactDaysToKeepStr: '', artifactNumToKeepStr: '5', daysToKeepStr: '', numToKeepStr: '5'))
}

stages{

  stage('CheckOutCode'){
    steps{
    git branch: 'master', credentialsId: 'Gittoken', url: 'https://github.com/maheshpothuganti/maven-web-application.git'
	
	}
  }
  
stage("build & SonarQube analysis") {
  steps {
   withSonarQubeEnv('SonarQube') {
     sh 'mvn clean package sonar:sonar'
              }
            }
          }
 }
 }


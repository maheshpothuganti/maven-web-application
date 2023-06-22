pipeline{

agent any

tools{
maven '3.6.3'

}

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
  
  stage('Build'){
  steps{
  sh  "mvn clean package"
  }
 }
 }
 }


pipeline{
  agent any
  stages{
    stage('stop old container'){
    steps{
      echo 'docker rm -r'
      checkout scm
    }
    stage('checkout code'){
    steps{
      echo 'pulling code from github'
      checkout scm
    }
       stage('build docker image'){
    steps{
      echo 'building docker image'+
      bat 'docker build -t company1website .'
    }
    }
      stage('run docker container')
      {
        steps{
          echo 'running docker container'
          bat 'docker run -d -p 8070:80 company1website'
        }
      }
  }
}

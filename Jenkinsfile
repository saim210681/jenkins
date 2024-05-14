pipeline {
   
    agent any
  environment{
     DOCKERHUB_CREDENTIALS=credentials('DockerHub')
  }
    stages{
        stage('Build'){
            steps{
                sh 'npm install'

            }
        }
        stage('test'){
            steps{
                sh 'echo "Test is running"'
            }
        }
        stage('Docker build'){
            steps{
                sh 'docker build -t saim210681/jenkins-integration:latest .'
            }
        }
        stage('login'){
            steps{
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('push'){
            steps{
                sh 'docker push saim210681/jenkins-integration:latest'
            }
        }
        stage('deploy'){
            steps{
                sh 'echo "Deploying the application"'
            }
        }
      
    }




}
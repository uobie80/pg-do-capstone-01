pipeline {
  agent any
  environment {
    PATH = "/usr/bin:$PATH"
    tag = '1.0'
    dockerHubUser = 'uobie80'
    containerName = 'asi-insure'
    httpPort = '8081'
  }
  stages {
    stage('code clone') {
        steps {
          checkout scmGit(branches: [[name: '*/main']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/uobie80/pg-do-capstone-01']]) 
          }
    }
    stage('Maven build') {
      steps {
         sh 'mvn clean install -DskipTests' }
    } 
    stage('Build Docker Image') {
      steps {
         sh "docker build -t ${dockerHubUser}/asi-insure:${tag} ." 
       }
      }
      stage('push image to dockerhub') {
      steps {
        withCredentials([usernamePassword(credentialsId: 'DockerHubUser', passwordVariable: 'dockerPassword', usernameVariable: 'dockerUser')]) {
          sh "docker login -u $dockerUser -p $dockerPassword"
          sh "docker push $dockerUser/$containerName:$tag" 
          } 
        }
       } 
       stage('Docker container deployment') {
      steps {
        sh "docker rm $containerName -f" sh "docker pull $dockerHubUser/$containerName:$tag"
        sh "docker run -d --rm -p $httpPort:$httpPort --name $containerName $dockerHubUser/$containerName:$tag"
        echo "Application started on port: ${httpPort} (http)" 
        } 
      } 
    }
  }


pipeline {
    environment {
    registry = "udhayashankard/nodeapp"
    registryCredential = 'docker-hub'
    dockerImage = ''
    }
    agent any
  stages {
    stage('Build result') {
      steps {
        sh 'docker build -t udhayashankard/result ./result'
      }
    } 
    stage('Build vote') {
      steps {
        sh 'docker build -t udhayashankard/vote ./vote'
      }
    }
    stage('Build worker') {
      steps {
        sh 'docker build -t udhayashankard/worker ./worker'
      }
    }
    stage('Push result image') {
      steps {
        withDockerRegistry(credentialsId: 'docker-hub', url:'') {
          sh 'docker push udhayashankard/result'
        }
      }
    }
    stage('Push vote image') {
      steps {
        withDockerRegistry(credentialsId: 'docker-hub', url:'') {
          sh 'docker push udhayashankard/vote'
        }
      }
    }
    stage('Push worker image') {
      steps {
        withDockerRegistry(credentialsId: 'docker-hub', url:'') {
          sh 'docker push udhayashankard/worker'
        }
      }
    }
  }
}

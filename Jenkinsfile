pipeline {
  agent any
  stages {
    stage('Récupération du code') {
      steps {
        checkout scm
        sh 'ls k8s'
      }
    }
    stage('Vérification du cluster') {
      steps {
        sh 'kubectl get nodes'
      }
    }
    stage('Déploiement sur Kubernetes') {
      steps {
        sh 'kubectl apply -f k8s/'
      }
    }
    stage('Vérification des pods') {
      steps {
        sh 'kubectl get pods -n food-delivery'
      }
    }
  }
}

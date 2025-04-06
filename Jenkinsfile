pipeline {
  agent any

  environment {
    DOCKER_COMPOSE_PATH = "./docker-compose.yml"
  }

  stages {
    stage('Checkout') {
      steps {
        git 'https://github.com/NdeyeCheikh03/projet_devops.git'
      }
    }

    stage('Build Docker Images') {
      steps {
        sh 'docker-compose build'
      }
    }

    stage('Run Containers') {
      steps {
        sh 'docker-compose up -d'
      }
    }

    stage('Tests') {
      steps {
        echo '⚙️ (Facultatif) Tu peux ajouter des tests ici'
      }
    }

    stage('Cleanup') {
      steps {
        echo '🧹 Tu peux faire docker-compose down ici si tu veux tout arrêter'
      }
    }
  }
}

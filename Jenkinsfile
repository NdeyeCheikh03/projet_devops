pipeline {
    agent any

    environment {
        PROJECT_NAME = "projet_devops"
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/NdeyeCheikh03/projet_devops.git', branch: 'main'
            }
        }

        stage('Build Docker Images') {
            steps {
                echo "🔧 Build des images Docker..."
                bat 'docker-compose build'
            }
        }

        stage('Run Containers') {
            steps {
                echo "🚀 Lancement des conteneurs..."
                bat 'docker-compose up -d'
            }
        }

        stage('Tests') {
            steps {
                echo "🧪 Tests"
                // Exemple : pour Laravel
                // bat 'docker exec projet_devops-backend-1 php artisan test'
            }
        }

        stage('Cleanup') {
            steps {
                echo "🧹 Nettoyage"
                // bat 'docker-compose down'
            }
        }
    }

    post {
        success {
            echo '✅ Déploiement réussi !'
        }
        failure {
            echo '❌ Une erreur est survenue.'
        }
    }
}

pipeline {
    agent any

    environment {
        PROJECT_NAME = "projet_devops"
    }

    stages {
        stage('Checkout') {
            steps {
                // Utiliser la branche main
                git url: 'https://github.com/NdeyeCheikh03/projet_devops.git', branch: 'main'
            }
        }

        stage('Build Docker Images') {
            steps {
                echo "🔧 Build des images Docker..."
                sh 'docker-compose build'
            }
        }

        stage('Run Containers') {
            steps {
                echo "🚀 Lancement des conteneurs..."
                sh 'docker-compose up -d'
            }
        }

        stage('Tests') {
            steps {
                echo "🧪 Ici, vous pouvez exécuter des tests unitaires ou e2e"
                // Exemple : Laravel tests
                // sh 'docker exec projet_devops-backend-1 php artisan test'
            }
        }

        stage('Cleanup') {
            steps {
                echo "🧹 Nettoyage si besoin"
                // Tu peux arrêter les conteneurs ici si ce n'est pas pour un env permanent
                // sh 'docker-compose down'
            }
        }
    }

    post {
        success {
            echo '✅ Déploiement terminé avec succès !'
        }
        failure {
            echo '❌ Une erreur est survenue pendant le pipeline.'
        }
    }
}

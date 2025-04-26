pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/deepakgitproject/wordpressjenkins.git'
            }
        }

        stage('Build & Deploy') {
            steps {
                script {
                    sh 'docker-compose down || echo "No containers to stop"'
                    sh 'docker-compose pull'
                    sh 'docker-compose up -d'
                }
            }
        }
    }

    post {
        always {
            echo '🚀 Deployment Pipeline Completed!'
        }
    }
}

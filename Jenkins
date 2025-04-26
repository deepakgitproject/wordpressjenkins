pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Replace with your actual repo URL
                git 'https://your-git-repo-link.git'
            }
        }

        stage('Build & Deploy') {
            steps {
                script {
                    // Stop containers (ignore errors), pull new images, then bring up services
                    sh 'docker-compose down || true'
                    sh 'docker-compose pull'
                    sh 'docker-compose up -d'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished'
        }
    }
}


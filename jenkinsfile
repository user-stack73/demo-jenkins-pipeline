pipeline {
    agent any

    stages {
        stage('Install dependencies') {
            steps {
                sh 'npm install'
            }
        }

        stage('Run tests') {
            steps {
                sh 'npm test'
            }
            post {
                always {
                    junit 'reports/junit.xml'
                }
            }
        }
    }

    post {
        success {
            echo '✅ Build et tests réussis oui!'
        }
        failure {
            echo '❌ Échec du pipeline ! Vérifie les logs.'
        }
    }
}

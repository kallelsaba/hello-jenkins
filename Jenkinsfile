pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Build (simulation)'
            }
        }

        stage('Test') {
            steps {
                echo 'Test du fichier index.html'
                bat 'if exist index.html (echo index.html existe) else (exit 1)'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement'
                bat 'mkdir "C:\\Users\\lenovo\\hello-jenkins-deploy" 2>nul'
                bat 'copy "%WORKSPACE%\\index.html" "C:\\Users\\lenovo\\hello-jenkins-deploy\\"'
            }
        }
    }

    post {
        success {
            echo 'Pipeline exécuté avec succès ✅'
        }
        failure {
            echo 'Pipeline échoué ❌'
        }
    }
}

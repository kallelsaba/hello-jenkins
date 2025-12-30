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
                bat 'if exist "%WORKSPACE%\\index.html" (echo index.html existe) else (exit 1)'
                bat 'type "%WORKSPACE%\\index.html"'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Déploiement'
                // Crée le dossier si nécessaire
                bat 'mkdir "C:\\Users\\lenovo\\hello-jenkins-deploy" 2>nul'
                // Copie index.html dans le dossier de déploiement
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

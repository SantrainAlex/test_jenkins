pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Clone le dépôt Git
                git 'https://github.com/votre-utilisateur/votre-depot.git'
            }
        }

        stage('Build') {
            steps {
                // Compile le projet avec Maven
                sh 'mvn clean install'
            }
        }

        stage('Test') {
            steps {
                // Exécute les tests unitaires
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                // Déploie l'application (par exemple, sur un serveur Tomcat)
                sh 'scp target/votre-application.war utilisateur@serveur:/path/to/deploy'
            }
        }
    }

    post {
        always {
            // Archive les rapports de test
            junit '**/target/surefire-reports/*.xml'
        }
    }
}

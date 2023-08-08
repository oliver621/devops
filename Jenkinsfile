pipeline {
 agent any
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/oliver621/devops.git'
                sh './mvnw compile'
            }
        }
        stage('package') {
            steps {
                sh './mvnw package'
            }
            post {
                success {
                    archiveArtifacts 'target/*.war'
                }
            }
        }
    }
}


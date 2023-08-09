pipeline {
 agent any
    stages {
        stage('Build') {
            steps {
                git 'https://github.com/oliversylvester/maven_java_web_example.git'
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

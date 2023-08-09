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
        }
        stage('deploy to tomcat') {
            steps {
                /* groovylint-disable-next-line LineLength */
                deploy adapters: [tomcat9(credentialsId: 'new', path: '', url: 'http://13.40.10.213:8080')], contextPath: 'tin', war: '**/*.war'
            }
        }
    }
}

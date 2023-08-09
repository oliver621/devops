pipeline {
    agent any

  

    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/oliversylvester/maven_java_web_example.git'

            }
            
        } 
        stage('stage1') {
            steps {
                // Get some code from a GitHub repository
                sh './mvnw compile'
            }
            
        }
        stage('package') {
            steps {
                // Get some code from a GitHub repository
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

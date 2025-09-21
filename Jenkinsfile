pipeline {
    agent any
    tools {
        maven 'Maven-3.9.11'   // match the name you configured in Jenkins Tools
        jdk 'jdk-17'           // match the JDK name in Jenkins Tools
    }
    stages {
        stage('Build') {
            steps {
                bat "mvn clean package"
            }
        }
    }
    post {
        always {
            archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
        }
    }
}

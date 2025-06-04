pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'mvn clean install'  // Use bat for Windows
            }
        }
    }
}

pipeline {
    agent any
    tools {
        maven 'Maven' // Should match name in Jenkins Global Tools
    }
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/your-repo/maven-project.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('Archive Artifact') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
        stage('Deploy Using Ansible') {
            steps {
                sh 'ansible-playbook -i inventory.ini deploy.yml'
            }
        }
    }
}

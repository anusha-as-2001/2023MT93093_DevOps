pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        
        stage('Build') {
            steps {
                echo 'Building...'
                sh 'mvn clean package'
            }
        }
        
        stage('Publish') {
            steps {
                echo 'Publishing...'
                sh 'cp target/*.jar artifacts/'
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up...'
            sh 'rm -rf artifacts/'
        }
    }
}

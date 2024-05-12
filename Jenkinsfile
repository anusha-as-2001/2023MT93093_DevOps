pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the code from Git repository
                git 'https://github.com/anusha-as-2001/2023MT93093_DevOps.git'
            }
        }
        stage('Build') {
            steps {
                // Perform any build steps here
                sh 'mvn clean package' // Assuming Maven for Java project, adjust as needed
            }
        }
        stage('Compile') {
            steps {
                // Perform any compilation steps here
                sh 'javac -d ./bin ./src/*.java' // Example compilation command for Java, adjust as needed
            }
        }
    }
    
    post {
        success {
            // If the pipeline runs successfully, you can trigger additional actions here
            echo 'Pipeline ran successfully!'
        }
        failure {
            // If the pipeline fails, you can trigger additional actions here
            echo 'Pipeline failed!'
        }
    }
}

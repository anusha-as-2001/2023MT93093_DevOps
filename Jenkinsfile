pipeline {
    agent any
    
    stages {
        stage('Declarative: Checkout SCM') {
            steps {
                checkout([$class: 'GitSCM', 
                    branches: [[name: 'master']], 
                    doGenerateSubmoduleConfigurations: false, 
                    extensions: [], 
                    submoduleCfg: [], 
                    userRemoteConfigs: [[url: 'https://github.com/anusha-as-2001/2023MT93081_Devops_A1.git']]
                ])
            }
        }
        
        stage('Initialize') {
            steps {
                echo 'Initializing...'
                // Add any initialization steps here
            }
        }
        
        stage('Build & Publish') {
            steps {
                echo 'Building...'
                // Add build steps here
                sh 'mvn clean package' // Example Maven build command, replace with actual build command
                
                echo 'Publishing...'
                // Add publish steps here
                sh 'cp target/*.jar artifacts/' // Example publishing step, replace with actual publish command
            }
        }
        
        stage('Upload to Azure Artifact') {
            steps {
                echo 'Uploading to Azure Artifact...'
                // Add steps to upload artifacts to Azure here
                sh 'az artifact push --file artifacts/*.jar --name <artifact_name> --version <version>' // Example Azure upload command, replace with actual upload command
            }
        }
    }
    
    post {
        always {
            echo 'Cleaning up...'
            // Add any cleanup steps here
            sh 'rm -rf artifacts/' // Example cleanup step, replace with actual cleanup command
        }
    }
}

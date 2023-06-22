pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout the repository with your branch
                checkout scm
            }
        }
        
        stage('Run Maven Project') {
            parallel {
                stage('Maven Build') {
                    steps {
                        // Run Maven build commands
                        sh 'mvn clean install'
                    }
                }
                
                stage('Retrieve Maven Version') {
                    steps {
                        // Retrieve Maven version
                        sh 'mvn --version'
                    }
                }
            }
        }
    }
}

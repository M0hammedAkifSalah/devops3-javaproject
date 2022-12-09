pipeline {
    
    agent any
    
    stages{
        stage('Git Checkout'){
            
            steps{
                git branch: 'main', url: 'https://github.com/M0hammedAkifSalah/devops3-javaproject.git'
            
            }
        
        }
        stage('Unit Testing'){
            
            steps{
                sh 'mvn test'
            
            }
        
        }
        stage('Maven Build'){
            
            steps{
                sh 'mvn clean install'
            
            }
        
        }
        stage('Static-Code-Analysis'){
            
            steps{
                script{
                     withSonarQubeEnv(credentialsId: 'sonar-api-key') {
                        sh'mvn clean package sonar:sonar'
                        }
                    
                }
            
            }
        
        }
        
        stage('Quality Gate Check'){
            
            steps{
                script{
                    waitForQualityGate abortPipeline: false, credentialsId: 'sonar-api-key'
                }
            
            }
        
        }
    }
}

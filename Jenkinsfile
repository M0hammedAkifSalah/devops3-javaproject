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
    }
}

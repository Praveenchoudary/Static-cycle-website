pipeline {
    agent any
    stages{
        stage("code"){
            steps {
                git "https://github.com/Praveenchoudary/static-cycle-website-jenkins-docker-.git"
            }
        }
        stage("build"){
            steps{
                sh "docker build -t praveen22233/cylcewebsite:v1 ."
            }
        }
        stage("push"){
            steps{
                script{
                    withDockerRegistry(credentialsId:'doccker') {
                        sh "docker push praveen22233/cylcewebsite:v1"
                        
                    }    
                }
            }
            
        }        
        stage("Container creation"){
            steps{
                sh "docker run -itd --name cyclecapp -p 1234:80 praveen22233/cylcewebsite:v1"
            }
        }
        
    }
    
}

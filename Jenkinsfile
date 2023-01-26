pipeline{
    agent any
    stages{
        stage("Sonar Quality Check"){
            agent {
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar-token') { //To work with sonarqube we have to set some env var
                        sh 'sudo chmod +x gradlew'
                        sh 'sudo ./gradlew sonarqube'
                    }
                }
            }
        }
    }
    
}
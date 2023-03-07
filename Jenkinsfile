pipeline{
    agent any
    stages{
        stage('git checkout'){
            steps{
                git credentialsId: 'raji_git', url: 'https://github.com/rajeeb007/sonarquality.git'
            }
        }
        stage('UNIT test'){
            steps{
                sh 'mvn test'
            }
        }
        stage('build'){
            steps{
                sh 'mvn clean install'
            }
        }
        stage('code analysis'){
            steps{
                script{
                    withSonarQubeEnv(credentialsId: 'sonar_api',installationName:'sonarqube') {
                        sh 'mvn sonar:sonar'
                    }
                }
            }
        }

    }
      
}
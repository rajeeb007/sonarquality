pipeline{
    agent any
    stages{
        stage('git checkout'){
            steps{
                git credentialsId: 'raji_git', url: 'https://github.com/rajeeb007/sonarquality.git'
            }
        }

    }
      
}
pipeline {
    agent { docker 'maven:3.8.1-adoptopenjdk-11' } 
    stages {
        stage('Example Build') {
            steps {
                sh 'mvn --version'
                sh 'sleep 120'
            }
        }
    }
}

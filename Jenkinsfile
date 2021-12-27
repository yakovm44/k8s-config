
pipeline {
    
    agent any
     
    stages {
        stage('build') {
            steps {
                echo "in build mode"
            }
        }
         stage('test') {
            steps {
                echo "in test mode"
            }
        }
    }
    post {
        always {
            echo " in the always"
        }
        success {
            echo " in the success"
        }
        failure {
            echo " in the fail"
        }
    }
}

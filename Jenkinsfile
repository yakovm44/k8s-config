
pipeline {
    
    agent any
     
    stages {
        stage('build') {
            when {
               
                expression{    
                    BRANCH_NAME == 'test1'
                }
            }
            steps {
                echo "in build mode , only for test1"
                echo "the build number is : $BUILD_NUMBER"
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

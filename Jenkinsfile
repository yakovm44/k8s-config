
pipeline {
    
    agent any
    
    parameters { 
        string(name: 'DEPLOY_ENV', defaultValue: 'staging', description: 'bla bla') 
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }
    environment{
    CHECKME=123
    CRED = credentials('yakov44-git')
    }
    
     
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
                echo "the build name is: $JOB_NAME  AAA $env.JOB_NAME"
                echo " the git url is: $GIT_URL"
                echo "1 check me = $CHECKME"
                echo '2 check me = $CHECKME'  //not work wall
                echo "3 check me = ${CHECKME}"
                
                echo " The credntiales = $CRED_USR" 
                echo " The credntiales = $CRED_PSW"
                echo " DEPLOY_ENV =$DEPLOY_ENV"
                
                 echo "111 Choice: ${params.CHOICE}"
                echo "222 Choice: ${CHOICE}"
                
                
            //    sh 'CHECKME=7777'
            //    echo " check me = $CHECKME"
                
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

pipeline {
    agent {
        docker { image 'node:14-alpine' }
    }
    stages {
        stage('Test') {
            steps {
                script {
                    ResultCode = sh (
                        returnStatus: true,
                        script: "./test.sh"
                    )
                    currentBuild.result = "SUCCESS"
                }   
                script {
                  if ( ResultCode == 1 ) {
                    echo "ERROR: plan failed"
                    exit 1
                  }
              } // script {}
           }
        }
    }
}
